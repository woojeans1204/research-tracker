# Research Tracker Team Spec

## Goal
Keep topic queues and logs consistent, and produce high-recall reasoning trend runs from the repo's canonical markdown and JSONL surfaces.

## Architecture
- Outer pattern: Expert Pool.
- Inner pattern for reasoning scout runs: Pipeline.
- Default style: single main agent. Do not add workers unless source acquisition is clearly independent and rate-limited.

## Inputs
- shared repo docs: `README.md`, `tracker-rules/*.md`, and topic files
- target topic name and decision type for queue or log updates
- date window, source list, query set, and record bounds for reasoning scout runs
- source links or metadata when a request touches a specific paper entry

## Outputs
- updated `topics/<topic>/reading-queue.md`, `paper-log.md`, or `tracker-rules.md`
- updated `runs/reasoning/raw/raw-records.jsonl`
- updated `runs/reasoning/processed/*`
- preserved `_workspace/` handoff notes when a task spans more than one phase

## File Ownership
- `topic-maintainer` owns `topics/<topic>/*` and `tracker-rules/global-rules.md`.
- `reasoning-scout` owns `runs/reasoning/*` and `tracker-rules/paper-scout-guide.md` plus `tracker-rules/run-file-format-rules.md`.
- `router` owns `_workspace/00_input/request-summary.md` and coordinates any handoff that crosses the two workflows.

## Roles
| Role | Responsibility | Reusable skill | Writes |
| --- | --- | --- | --- |
| router | classify the request, capture the minimal summary, and choose the workflow branch | `.agents/skills/research-tracker-orchestrator/SKILL.md` | `_workspace/00_input/request-summary.md` |
| topic-maintainer | normalize queue, log, shared topic policy, and topic-rule changes | `.agents/skills/topic-maintainer/SKILL.md` | `topics/<topic>/*`, `tracker-rules/global-rules.md`, and optional `_workspace/topic-maintenance/<topic>/change-log.md` |
| reasoning-scout | collect, process, classify, and report a reasoning corpus run | `.agents/skills/reasoning-scout/SKILL.md` | `runs/reasoning/raw/raw-records.jsonl`, `runs/reasoning/processed/*`, `tracker-rules/paper-scout-guide.md`, `tracker-rules/run-file-format-rules.md`, and optional `_workspace/reasoning-scout/<run>/review-notes.md` |

## Phase Order

### Topic Maintenance
1. Read `tracker-rules/global-rules.md` and the target topic's `tracker-rules.md`.
2. Decide whether the change belongs in `reading-queue.md`, `paper-log.md`, or the topic rules file.
3. Update the target file or files, including `Last updated`.
4. Run a consistency pass for allowed statuses, required fields, and one-item-per-entry.
5. If the request is ambiguous, stop before inventing metadata and note the uncertainty in `_workspace/topic-maintenance/<topic>/questions.md`.

### Reasoning Scout
1. Capture run parameters in `_workspace/reasoning-scout/<run>/request-summary.md`.
2. Collect broad metadata into `runs/reasoning/raw/raw-records.jsonl`.
3. Normalize, deduplicate, and apply the minimal quality gate.
4. Enrich, classify relevance, and build paper cards.
5. Discover clusters and summarize trends.
6. Write `processing-summary.md` and `trend-report.md`.
7. Run a final QA check against counts, coverage, raw-file purity, and incomplete-coverage disclosure.

## Handoff Files
| From | To | File | Purpose |
| --- | --- | --- | --- |
| router | topic-maintainer | `_workspace/00_input/request-summary.md` | capture the topic, target file, and desired decision |
| router | reasoning-scout | `_workspace/00_input/request-summary.md` | capture the run window, sources, query set, and output target |
| reasoning-scout | router | `runs/reasoning/processed/processing-summary.md` | count reconciliation and provenance check |
| reasoning-scout | router | `runs/reasoning/processed/trend-report.md` | final analysis artifact that must mention incomplete coverage when applicable |

## Failure Policy
- retry policy: one targeted retry for malformed metadata, missing counts, or a transient source timeout; do not loop indefinitely.
- partial completion policy: if the request can be made safe without guessing, write the safe subset and leave the unknowns in `_workspace/`.
- conflict resolution policy: shared rules win over topic-specific rules; topic-specific rules win over ad hoc preferences.
- escalation trigger: if a request would require deleting unrelated files, changing repository policy, or inferring missing paper facts, stop and ask.

## Removable Model-Specific Logic
- source retry backoff for slow metadata APIs.
- title-only classification fallback when abstracts are unavailable.
- deletion trigger: remove these heuristics if the repo later switches to a different source layer or stronger metadata coverage.

## Validation Checks
- topic files use only allowed statuses and required fields.
- `Last updated` changes in every edited topic or run file.
- raw reasoning records remain collection-only JSONL with required fields in order.
- counts in `processing-summary.md` match the processed files.
- `trend-report.md` explicitly notes incomplete coverage when the corpus is partial.
- queue and log entries never mix raw crawl output with curated notes.

## Optional Worker Delegation Notes
- safe parallel slices: independent source discovery only, when rate limits permit.
- forbidden overlaps: two agents writing the same raw JSONL or the same topic file at once.
- synthesis owner: the main orchestrator or reasoning-scout skill.

## Test Scenarios
### Normal flow
- request: add a new paper to `topics/reasoning/reading-queue.md`.
- expected phase outputs: updated queue entry, updated `Last updated`, no raw crawl artifacts.
- expected final output: concise confirmation naming the edited files.

### Failure flow
- failure point: a run request omits the date window or source list.
- expected fallback behavior: write a request-summary stub, do not fabricate the corpus, and ask for the missing parameter only if it cannot be inferred from the repo.
- expected reporting: note which downstream files were intentionally not written.
