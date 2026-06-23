# Paper Log

Last updated: 2026-06-23

## Read

### [2026-06-23] Plan and Budget: Effective and Efficient Test-Time Scaling on Reasoning Large Language Models
- Link: https://openreview.net/forum?id=ctspw4CqbS
- Source: ICLR 2026 Poster / OpenReview
- Recommended by: agent
- Decision: read
- Priority: high
- Topic tags: reasoning, inference-time-scaling, test-time-compute, planning, efficiency
- Broader trend: adaptive and controllable test-time compute for LLM reasoning

#### Why this paper
- It gives a structured view of test-time scaling as planning plus token-budget allocation, rather than simply generating longer chains or more samples.
- It is relevant as a reference point for reasoning systems that try to spend inference compute where it is most useful.

#### Core idea
- Decompose a reasoning problem into sub-questions before spending the reasoning budget.
- Estimate sub-question difficulty or uncertainty and allocate more tokens to harder parts.
- Evaluate reasoning quality together with token efficiency, not accuracy alone.

#### Critical notes
- The theory and framing look promising, but the key open question is whether the theoretical allocation story is actually realized cleanly in practice.
- Need to inspect the code implementation to judge how much of the gain comes from the proposed theory versus implementation details, prompting choices, or benchmark-specific effects.
- Planning and decomposition quality may be doing a lot of hidden work, so implementation details matter for interpreting the empirical results.

#### Related papers
- CaTS: Calibrated Test-Time Scaling for Efficient LLM Reasoning - https://openreview.net/forum?id=jrSc4RJXy1
- What If We Allocate Test-Time Compute Adaptively? - https://arxiv.org/abs/2602.01070

#### Personal notes
- User read it and thought it looked good overall, but is not fully convinced yet that the theory has been applied effectively in the actual system.
- Next step: inspect the released code implementation before treating the method as practically validated.

## Skimmed

### [YYYY-MM-DD] Paper Title
- Link:
- Source:
- Recommended by: agent | manual
- Decision: skim
- Priority: high | medium | low
- Topic tags:
- Broader trend:

#### Why this paper
- 

#### Core idea
- 
- 
- 

#### Critical notes
- 
- 

#### Related papers
- 
- 

#### Personal notes
- 

## Skipped

### [YYYY-MM-DD] Paper Title
- Link:
- Source:
- Recommended by: agent | manual
- Decision: skip
- Priority: high | medium | low
- Topic tags:
- Broader trend:

#### Why this paper
- 

#### Critical notes
- 
- 

#### Personal notes
- 

## Archived
