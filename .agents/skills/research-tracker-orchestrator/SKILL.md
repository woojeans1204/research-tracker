---
name: research-tracker-orchestrator
description: Route research-tracker work to topic maintenance or reasoning scout workflows and preserve deterministic handoffs.
---

# Research Tracker Orchestrator

## When to Use
- use this skill for repo-wide research-tracker requests that may touch topic files, tracker rules, or reasoning runs
- use it when you need to decide whether work belongs in topic maintenance or the reasoning scout pipeline
- do not use it for a request that is already clearly limited to one specialist and one file set

## Required Inputs
- target topic name or run name, if known
- requested artifact or file surface
- paper metadata, links, or topic notes when the task is content-bearing
- date window, source list, and query set when the task is a reasoning run

## Workflow
1. Classify the request as topic maintenance, reasoning scout, or repo-policy edit.
2. Write or refresh `_workspace/00_input/request-summary.md` with the minimal task summary.
3. Route the task using `docs/harness/research-tracker/team-spec.md`.
4. Hand topic updates and shared topic policy edits to `topic-maintainer`.
5. Hand reasoning runs and reasoning scout policy edits to `reasoning-scout`.
6. Confirm the specialist validation checks pass before returning a completion note.

## Outputs
- `_workspace/00_input/request-summary.md`
- updated topic files or reasoning run artifacts
- a short completion note that names the changed paths

## Validation
- the chosen route matches the requested file surface
- outputs stay on the repo's canonical paths
- raw reasoning data is never mixed into curated topic files
