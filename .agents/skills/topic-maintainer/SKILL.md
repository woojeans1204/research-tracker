---
name: topic-maintainer
description: Maintain research-tracker topic queues, paper logs, and topic-specific tracker rules with consistent markdown structure.
---

# Topic Maintainer

## When to Use
- use this skill when a request updates `topics/<topic>/reading-queue.md`, `paper-log.md`, or `tracker-rules.md`
- use it when a topic needs a new queued paper, a finalized log entry, or a topic-specific rule change
- use it when a request updates `tracker-rules/global-rules.md` or adds a new topic folder with the canonical three files
- do not use it for raw crawl processing or trend analysis over `runs/reasoning/`

## Required Inputs
- topic name
- target file or decision type: queue, log, or topic rules
- paper metadata, links, or decision notes
- any topic-specific exception that must override the shared rules

## Workflow
1. Read `tracker-rules/global-rules.md` and the target topic's `tracker-rules.md`.
2. Decide whether the item belongs in `reading-queue.md`, `paper-log.md`, or the topic rules file.
3. Preserve the repo's one-item-per-entry format and keep links near the top of each entry.
4. Leave extra scratch notes such as `ideas.md` alone unless the request explicitly names them.
5. Update `Last updated` in every topic file you touch.
6. If the change is ambiguous, stop before inventing metadata and write the uncertainty in `_workspace/topic-maintenance/<topic>/questions.md`.

## Outputs
- updated `topics/<topic>/reading-queue.md`
- updated `topics/<topic>/paper-log.md`
- updated `topics/<topic>/tracker-rules.md`
- updated `tracker-rules/global-rules.md` when the shared topic policy changes
- optional `_workspace/topic-maintenance/<topic>/change-log.md`

## Validation
- queue entries use only `queued` or `reading`
- log entries use only `read`, `skimmed`, `skipped`, or `archived`
- required fields are present for the target file type
- `Last updated` changed in every edited topic file
- no raw crawl records are copied into curated topic notes
