# Research Tracker

A reusable Markdown-based repository for tracking papers, reading queues, and topic-specific research notes.

## Purpose

This repository is designed to manage multiple research topics with a consistent structure.

Each topic keeps:
- an active reading queue
- a paper log for completed or skipped papers
- local tracking rules when needed

## Repository Structure

```text
research-tracker/
  README.md
  tracker-rules/
    global-rules.md
    paper-scout-guide.md
  topics/
    reasoning/
      reading-queue.md
      paper-log.md
      tracker-rules.md
```

## Topic Structure

Each topic should use the same base structure:

```text
topics/<topic-name>/
  reading-queue.md
  paper-log.md
  tracker-rules.md
```

## File Roles

- `reading-queue.md`: active candidates to read
- `paper-log.md`: completed, skimmed, skipped, or archived entries
- `tracker-rules.md`: topic-specific rules or exceptions
- `tracker-rules/global-rules.md`: shared rules across all topics
- `tracker-rules/paper-scout-guide.md`: reusable workflow for API-based LLM reasoning trend-corpus collection and synthesis

## How To Add A New Topic

1. Create a new folder under `topics/`
2. Add:
   - `reading-queue.md`
   - `paper-log.md`
   - `tracker-rules.md`
3. Follow the shared rules in `tracker-rules/global-rules.md`
4. Add topic-specific exceptions only if needed

## Naming Rules

- Use lowercase topic names
- Avoid spaces
- Use hyphens if needed

Examples:
- `reasoning`
- `agent-evals`
- `test-time-compute`

## Operating Principle

Keep the system simple:
- queue first
- log after decision
- rules stay explicit
- one item per entry
