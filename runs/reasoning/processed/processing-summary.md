# Processing Summary

Generated: 2026-06-26

## Pipeline

1. Normalized raw records.
2. Deduplicated by exact normalized title.
3. Applied minimal quality gate over id, title, link, date, and source.
4. Enriched Semantic Scholar records with abstract, authors, venue, publication types, and external IDs.
5. Classified relevance from title+abstract where available; title-only otherwise.
6. Built paper cards for central and adjacent records without quoting abstracts.
7. Discovered provisional clusters and summarized trends.

## Counts

- Raw records: 2000
- Dedupe dropped: 0
- Quality dropped: 0
- Enriched records: 2000
- Abstract available: 1308
- Central: 1468
- Adjacent: 304
- Noise: 228
- Paper cards: 1772

## Generated Files

- `runs/reasoning/processed/normalized-records.jsonl`
- `runs/reasoning/processed/deduped-records.jsonl`
- `runs/reasoning/processed/dedupe-dropped-records.jsonl`
- `runs/reasoning/processed/minimal-quality-records.jsonl`
- `runs/reasoning/processed/quality-dropped-records.jsonl`
- `runs/reasoning/processed/enriched-records.jsonl`
- `runs/reasoning/processed/relevance-classified-records.jsonl`
- `runs/reasoning/processed/paper-cards.jsonl`
- `runs/reasoning/processed/paper-cards.md`
- `runs/reasoning/processed/clusters.md`
- `runs/reasoning/processed/trend-report.md`
- `runs/reasoning/processed/processing-summary.md`

## Caveats

- arXiv abstracts are not available in this pass because the arXiv API timed out during enrichment.
- Evidence quality, baseline quality, code availability, and venue/review signals remain conservative and mostly `unclear`.
- Cluster names are provisional. They should be reviewed after a stronger judgment pass.
