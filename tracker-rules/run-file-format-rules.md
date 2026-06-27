# Run File Format Rules

Last updated: 2026-06-26

## Purpose

This file defines the format for raw broad-metadata snapshots produced by reasoning crawl runs.

The raw stage is collection-only. It should not contain analysis judgments, cluster labels, or recommendation language.

## Scope

Applies to:

- `runs/reasoning/raw/raw-records.jsonl`

Not covered here:

- paper cards
- trend notes
- cluster drafts
- reading queues
- paper logs

## File Format

`raw-records.jsonl` is a UTF-8 JSON Lines file.

Rules:

- One JSON object per line.
- No trailing commas.
- No blank lines.
- No Markdown wrappers.
- No array wrapper around the file.
- Keep field names stable across records.

## Required Fields

Every record must include:

- `id`
- `title`
- `link`
- `date`
- `source`

Field meaning:

- `id`: source-local stable identifier, preferably without a URL prefix.
- `title`: paper title as a plain string.
- `link`: stable abstract or landing-page URL.
- `date`: source date in `YYYY-MM-DD` format when available; `YYYY-MM` is allowed only if the source does not expose a day.
- `source`: source name such as `arXiv`, `OpenReview`, or `Semantic Scholar`.

## Optional Fields

Optional metadata fields may be added later if the source provides them and they stay in the broad-metadata stage:

- `authors`: array of author strings
- `abstract`: plain-text abstract
- `categories`: array of source categories
- `comment`: source comment or note
- `query`: query string or route used to fetch the record
- `fetched_at`: UTC timestamp in ISO-8601 format

If optional fields are added, keep them descriptive only. Do not add:

- `relevance`
- `method_type`
- `trend_signal`
- `cluster`
- `priority`
- `quality`
- `decision`

Those belong to later analysis files, not raw metadata snapshots.

## Field Order

Use this order for the first five fields:

1. `id`
2. `title`
3. `link`
4. `date`
5. `source`

If optional fields are present, append them after the required fields in a consistent order.

## Example

```json
{"id":"2606.20227","title":"QMFOL: Benchmarking Large Language Model Reasoning via Quantifiable Monadic First-Order Logic Test Case Generation","link":"https://arxiv.org/abs/2606.20227","date":"2026-06-18","source":"arXiv"}
```

## Minimal Quality Gate

Keep a record in the raw file only if it has:

- a stable identifier
- a title
- a stable link
- a date in acceptable source granularity
- a source label

Records that fail these checks should not be written into `raw-records.jsonl`.
