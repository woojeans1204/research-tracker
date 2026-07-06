---
name: reasoning-scout
description: Collect, process, classify, and report recent LLM reasoning papers into the research-tracker run format.
---

# Reasoning Scout

## When to Use
- use this skill for `runs/reasoning/` collection and analysis work
- use it when the goal is to build or refresh the reasoning trend corpus, paper cards, clusters, or trend report
- use it when a request updates `tracker-rules/paper-scout-guide.md` or `tracker-rules/run-file-format-rules.md`
- do not use it for topic queue maintenance unless the request explicitly needs a reading queue follow-up

## Required Inputs
- date window
- source list
- query set
- record limits or other collection bounds
- whether PDFs are allowed, which should default to no

## Workflow
1. Read `tracker-rules/paper-scout-guide.md`, `tracker-rules/run-file-format-rules.md`, and `tracker-rules/global-rules.md`.
2. Record the run parameters in `_workspace/reasoning-scout/<run>/request-summary.md`.
3. Collect broad metadata into `runs/reasoning/raw/raw-records.jsonl` only.
4. Normalize, deduplicate, and apply the minimal quality gate.
5. Enrich records, classify relevance, and build paper cards.
6. Discover clusters and write the trend report and processing summary.
7. Run a final QA pass on counts, raw-file purity, and coverage disclosure.

## Outputs
- `runs/reasoning/raw/raw-records.jsonl`
- `runs/reasoning/processed/normalized-records.jsonl`
- `runs/reasoning/processed/deduped-records.jsonl`
- `runs/reasoning/processed/minimal-quality-records.jsonl`
- `runs/reasoning/processed/enriched-records.jsonl`
- `runs/reasoning/processed/relevance-classified-records.jsonl`
- `runs/reasoning/processed/paper-cards.jsonl`
- `runs/reasoning/processed/paper-cards.md`
- `runs/reasoning/processed/clusters.md`
- `runs/reasoning/processed/trend-report.md`
- `runs/reasoning/processed/processing-summary.md`
- updated `tracker-rules/paper-scout-guide.md` or `tracker-rules/run-file-format-rules.md` when the run policy changes
- optional `_workspace/reasoning-scout/<run>/review-notes.md`

## Validation
- raw records stay collection-only JSONL with the required field order
- analysis fields never appear in `runs/reasoning/raw/raw-records.jsonl`
- counts in `processing-summary.md` match the processed artifacts
- `trend-report.md` states when coverage is incomplete
- PDFs are skipped by default
- source claims remain linked to a source record rather than model memory
