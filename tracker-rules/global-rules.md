# Global Rules

## Purpose

These rules apply across all topics in this repository.

Use them to keep topic folders consistent, lightweight, and easy to update.

## Standard Topic Structure

Every topic should follow this structure:

```text
topics/<topic-name>/
  reading-queue.md
  paper-log.md
  tracker-rules.md
```

## Required Files

Each topic must include:

- `reading-queue.md`
- `paper-log.md`
- `tracker-rules.md`

## File Definitions

### `reading-queue.md`
Used for active candidates that have not been finalized yet.

Allowed statuses:
- `queued`
- `reading`

### `paper-log.md`
Used for finalized entries.

Allowed statuses:
- `read`
- `skimmed`
- `skipped`
- `archived`

### `tracker-rules.md`
Used for topic-specific rules only.

Do not duplicate general repository-wide rules here unless necessary.

## Required Fields For Queue Entries

Each queue entry should include:

- Title
- Link
- Added date
- Priority
- Status
- Topic tags
- Why now

## Required Fields For Log Entries

Each log entry should include:

- Title
- Date
- Link
- Source
- Recommended by
- Decision
- Priority
- Topic tags
- Broader trend

Recommended sections:
- Why this paper
- Core idea
- Critical notes
- Related papers
- Personal notes

## Writing Rules

- One item per entry
- Keep links near the top
- Prefer short bullets over long paragraphs
- Keep headings consistent
- Do not mix active queue items into the paper log
- Move an item from queue to log after a reading decision is made

## Priority Definitions

- `high`: read soon
- `medium`: useful but not urgent
- `low`: optional

## Update Rules

- Update `Last updated` whenever a file changes
- Add new candidates only to `reading-queue.md`
- Move completed or skipped items to `paper-log.md`
- Keep topic-specific exceptions inside the local `tracker-rules.md`

## Topic Tag Rules

Topic tags should be short and reusable.

Examples:
- `reasoning`
- `planning`
- `verification`
- `agent`
- `eval`
- `benchmark`
- `tool-use`
- `search`

## Consistency Rule

If a topic needs a special workflow, add it to that topic's `tracker-rules.md` without breaking the shared file structure.
