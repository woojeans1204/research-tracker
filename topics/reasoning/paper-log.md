# Paper Log

Last updated: 2026-06-27

## Recommendation Guidance

### [2026-06-27] Diversify beyond test-time scaling
- User feedback: stop over-recommending test-time scaling / test-time compute papers for now.
- Before recommending the next paper, check `runs/reasoning/processed/trend-report.md` and deliberately sample from other visible clusters.
- Near-term recommendation priority should shift toward multimodal reasoning, agentic planning, evaluation/benchmarks, knowledge-grounded reasoning, training/distillation, robustness, domain reasoning, or code/tool reasoning.
- Only recommend another test-time scaling paper if it is clearly exceptional, directly answers an active user question, or contrasts sharply with the already-read papers.
- Avoid treating "reasoning = test-time compute" as the default frame.

## Read

### [2026-06-26] e3: Learning to Explore Enables Extrapolation of Test-Time Compute for LLMs
- Link: https://matthewyryang.github.io/e3/
- Source: uploaded PDF / ICLR 2026 conference paper
- Recommended by: manual
- Decision: read
- Priority: medium-high
- Topic tags: reasoning, RLVR, test-time-compute, extrapolation, curriculum, negative-gradient, analysis-paper
- Broader trend: explaining when RL-trained reasoning models can actually extrapolate beyond their training token budget

#### Why this paper
- Useful as an example of reframing a relatively simple training recipe around a sharper research question: why test-time compute scaling often fails to extrapolate beyond the training budget.
- The main value is not a radically new optimizer or code-level algorithm, but a clean analytical story connecting asymmetries, negative gradients, curriculum design, and extrapolation behavior.

#### Core idea
- e3 argues that models extrapolate test-time compute better when they learn in-context exploration rather than merely producing longer traces.
- The recipe relies on three ingredients: base-model asymmetries such as a verification-generation gap, keeping negative gradients from incorrect traces during RL, and coupling task difficulty with training token budget through curriculum.
- Practically, this looks closer to finding a training configuration and budget/data schedule that encourages extrapolation than introducing a fundamentally new learning algorithm.

#### Critical notes
- Initial reaction: somewhat deflating technically, because the concrete intervention seems closer to parameter/budget/curriculum search than a major new algorithmic contribution.
- Working critique: the paper's actual method may be "not doing that much" at the code/intervention level; a lot of the contribution is in how the authors define the failure mode and organize the analysis around extrapolation.
- Still, the paper is valuable because it gives a solid causal-looking narrative: current models fail extrapolation, asymmetry enables useful internal feedback, negative gradients lengthen and diversify traces, and a coupled curriculum preserves exploration without making RL optimization too hard.
- The important lesson for my own research is that a paper can be strong if it turns a modest recipe into a disciplined argument with controlled ablations, mechanism hypotheses, and a clear evaluation regime.

#### Related papers
- Plan and Budget: Effective and Efficient Test-Time Scaling on Reasoning Large Language Models - https://openreview.net/forum?id=ctspw4CqbS
- Beyond Magnitude: Leveraging Direction of RLVR Updates for LLM Reasoning - https://openreview.net/forum?id=r6Pw3RiMYL

#### Personal notes
- The key takeaway is not "e3 is a surprising new algorithm," but "the authors made a solid research contribution by structuring the question well."
- For future research writing, use this as a template: identify a real failure regime, introduce the right diagnostic axis, propose a mechanism, verify it through ablations, then present the final recipe as the consequence of the analysis.
- This is a good reminder that strong paper construction can make even a seemingly modest intervention feel meaningful when the logic and evidence are tight.

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
- Code inspection suggests the implementation is closer to budget-aware prompting than hard budget allocation: decomposition is precomputed, credits and a decay schedule are used to calculate per-subquestion budgets, and those budgets are inserted into a single prompt as instructions such as "up to N words."
- The model is not modified or fine-tuned, subquestions are not solved through separate API calls, and per-subquestion token limits are not enforced through hard decoding constraints. This makes the practical budget-control claim weaker than the theoretical BAM framing might suggest.
- A central concern remains whether black-box LLMs meaningfully distinguish soft prompt instructions like "under 500 tokens" versus "under 1000 tokens," or whether this mostly changes verbosity rather than actual reasoning allocation.
- Follow-up question: are other token-budget allocation papers also implemented mostly as prompt-level budget hints, or do some actually control inference variables such as max tokens, sample count, search width/depth, verifier calls, or stopping rules?

#### Related papers
- CaTS: Calibrated Test-Time Scaling for Efficient LLM Reasoning - https://openreview.net/forum?id=jrSc4RJXy1
- What If We Allocate Test-Time Compute Adaptively? - https://arxiv.org/abs/2602.01070

#### Personal notes
- User read it and thought it looked good overall, but is not fully convinced yet that the theory has been applied effectively in the actual system.
- Next step: inspect the released code implementation before treating the method as practically validated.
- After inspecting the code flow, the user felt disappointed: the implementation seems to compute token allocation and then mostly express it as prompt text, which feels like a relatively shallow intervention compared with the paper's theoretical framing.
- User's working critique: "This looks like prompt tweaking with calculated token allocation. The broader question is whether budget management itself is fundamentally shaky if the control channel is just natural-language instructions to the LLM."

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
