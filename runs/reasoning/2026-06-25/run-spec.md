# LLM Reasoning Scout Run

Last updated: 2026-06-25

## Run Parameters

- Topic: reasoning
- Run date: 2026-06-25
- Date window: 2026-05-26 to 2026-06-25
- Target repository path: `runs/reasoning/2026-06-25/`
- Sources used: arXiv abstract pages and indexed arXiv metadata/search snippets
- Sources attempted: arXiv API from the execution container
- PDF download: skipped
- Output mode: high-recall seed crawl, not a ranked recommendation list

## Access Note

Direct calls from the execution container to `export.arxiv.org` were blocked by a network CONNECT 403. Because of that, this run uses accessible arXiv abstract metadata and search-indexed snippets rather than a full arXiv API pull. Coverage is incomplete and should be treated as a seed corpus for trend analysis, not a complete 30-day crawl.

## Query Set

- `large language model` AND `reasoning`
- `LLM` AND `reasoning`
- `test-time` AND `reasoning` AND `large language`
- `chain-of-thought` AND `LLM`
- `verification` AND `LLM reasoning`

## Minimal Quality Gate

Included records have title, stable arXiv link, apparent submission date in the run window, and enough metadata/snippet text to judge rough relevance.

Excluded or deprioritized records were outside the date window, obvious non-LLM papers, or records where `reasoning` was only incidental.

## Count Summary

- Raw candidate records retained: 42
- Central records: 37
- Adjacent records: 5
- Noise records retained in cards: 0

## Caveats

- No citation counts were collected.
- No OpenReview review signal was collected.
- Venue and acceptance claims are only included when visible in arXiv metadata snippets.
- Evidence and baseline quality labels are rough metadata-level annotations, not deep paper reviews.
