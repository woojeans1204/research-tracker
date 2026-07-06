# Research Tracker Agents Guide

Keep this file short and repo-wide. Use `tracker-rules/*.md` for workflow policy and `docs/harness/research-tracker/team-spec.md` for routing.

## What
- Markdown repository for tracking research topics, reading queues, paper logs, and reasoning trend runs.
- Canonical surfaces: `topics/<topic>/`, `runs/reasoning/`, and `tracker-rules/`.
- Keep raw crawl snapshots separate from curated reading notes.

## Why
- The repo preserves a high-recall paper memory with explicit decisions.
- Topic folders must stay consistent so future runs can be compared.
- Reasoning scout output is analysis, not a queue, so raw metadata and curated notes stay separated.

## How
- Follow `tracker-rules/global-rules.md` for topic structure and status values.
- Follow `tracker-rules/paper-scout-guide.md` and `tracker-rules/run-file-format-rules.md` for reasoning runs.
- Update `Last updated` in any topic or run file you edit.
- Add new candidates only to `reading-queue.md`; move finalized entries to `paper-log.md`.
- Keep `runs/reasoning/raw/raw-records.jsonl` collection-only and store analysis under `runs/reasoning/processed/`.
- Treat extra topic-local scratch notes such as `ideas.md` as optional unless the request explicitly names them.
- Use `docs/harness/research-tracker/team-spec.md` when a request could touch more than one workflow.
