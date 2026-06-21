# Topic Rules

## Scope
- Track recent diffusion language model papers and closely related work.
- Include topics such as discrete diffusion for text, masked diffusion language modeling, diffusion-based sequence generation, iterative refinement, non-autoregressive generation with diffusion-style objectives, controllability, editing, inference methods, and evaluations against autoregressive language models.

## Inclusion Rules
- Prefer papers from the last 6 months.
- Prefer papers with strong experimental quality, meaningful baselines, and clear validation signals.
- Prefer work that is centrally about diffusion language models, not only loosely adjacent.

## Exclusion Rules
- Do not add papers older than the active recency window unless explicitly requested.
- Do not prioritize hype over evidence quality.
- Do not log papers that are only weakly related to diffusion language models without noting the reason.

## Preferred Topic Tags
- diffusion-language-models
- discrete-diffusion
- masked-diffusion
- iterative-refinement
- non-autoregressive-generation
- controllability
- text-generation
- diffusion-inference
- language-modeling

## Storage Mode
- Use a mixed tracking model.
- Save each daily recommendation response to a date-based Markdown archive.
- Keep `reading-queue.md` selective rather than exhaustive.
- Keep `paper-log.md` limited to papers the user has explicitly resolved.

## Workflow Notes
- Save the recommendation answer for the day into a daily Markdown file under `topics/diffusion-language-models/daily/` using a date-based filename.
- If the date-based daily file already exists, append the new recommendation entry to that same file instead of creating a second file.
- Do not create duplicate date variants such as `YYYY-MM-DD-2.md` unless the user explicitly asks for a different convention.
- Add a clear section break or timestamped subsection when appending another entry to an existing daily file.
- Create or update the daily file automatically when a daily recommendation is delivered and the user wants GitHub sync behavior active.
- Add papers to `reading-queue.md` only when the user explicitly asks to save, queue, or track that paper there.
- Move or add papers to `paper-log.md` only when the user explicitly says they read the paper, finished it, or want to skip it.
- Treat user statements such as `I read this`, `mark as read`, `skip this`, or equivalent as explicit log-update instructions.
- Update `Last updated` whenever a tracker file changes.
- Keep entries compact and consistent.
