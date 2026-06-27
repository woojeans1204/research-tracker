# LLM Reasoning Trend Report

Generated: 2026-06-26

## Scope and Coverage

- Date window: 2026-05-27 to 2026-06-26
- Query set: broad LLM reasoning, language model reasoning, chain-of-thought, test-time reasoning/scaling, benchmarks, multimodal/VLM reasoning, agent reasoning, verification, planning, tool use, and high-recall Semantic Scholar follow-up queries.
- Sources used: arXiv and Semantic Scholar. Source counts: arXiv 622, Semantic Scholar 1378.
- Total records collected: 2000 after dedupe and minimal quality gate.
- Abstract coverage: 1308/2000 records; Semantic Scholar abstracts 1308/1378; arXiv abstracts not fetched because arXiv API timed out during this pass.
- Number of central papers: 1468
- Number of adjacent papers: 304
- Number of noise papers: 228
- Coverage note: incomplete. The classification is stronger than title-only for Semantic Scholar records with abstracts, but venue acceptance, code links, baseline quality, and experimental strength are not verified.

## Main Clusters

- Multimodal, visual, video, and spatial reasoning: 393 records (313 central, 80 adjacent).
- Agentic planning, orchestration, and multi-agent reasoning: 388 records (331 central, 57 adjacent).
- General LLM reasoning frameworks and methods: 246 records (186 central, 60 adjacent).
- Evaluation, benchmarks, and question answering: 220 records (181 central, 39 adjacent).
- Knowledge, retrieval, graph, and evidence-grounded reasoning: 139 records (122 central, 17 adjacent).
- Training, distillation, and optimization for reasoning: 125 records (104 central, 21 adjacent).
- Test-time scaling, search, verification, and self-correction: 74 records (66 central, 8 adjacent).
- Mathematical, logical, formal, and symbolic reasoning: 58 records (52 central, 6 adjacent).
- Robustness, safety, faithfulness, and failure analysis: 53 records (44 central, 9 adjacent).
- Domain-specific scientific, medical, clinical, and legal reasoning: 44 records (43 central, 1 adjacent).
- Code, tool, and program reasoning: 32 records (26 central, 6 adjacent).

## Repeated Claims and Common Framing

Most repeated title phrases among central/adjacent records:

- `language models`: 276
- `large language`: 263
- `large language models`: 215
- `language model`: 68
- `vision-language models`: 47
- `large language model`: 43
- `question answering`: 43
- `reinforcement learning`: 41
- `llm agents`: 39
- `llm reasoning`: 38
- `reasoning large`: 22
- `multimodal large`: 22
- `multimodal large language`: 22
- `reasoning large language`: 21
- `reasoning models`: 20
- `policy optimization`: 19
- `spatial reasoning`: 19
- `reasoning llms`: 18
- `knowledge graph`: 16
- `multimodal llms`: 15

The corpus is not concentrated in one subtopic. Reasoning is being used as an evaluation target, an agent-control property, a multimodal capability, a domain-transfer claim, and a training/inference-time intervention. This makes it useful for trend analysis, but it also means the central/adjacent split should be treated as a first pass.

## Common Benchmark and Evaluation Patterns

- Benchmark/evaluation language is a major visible signal, especially around legal reasoning, visual QA, clinical QA, software-agent reasoning, and broad LLM capability tests.
- QA-style tasks remain a common proxy for reasoning, including multi-hop, visual, medical, legal, and code-related variants.
- Baseline strength and benchmark novelty are still unknown without deeper paper review.

## Weak or Hype-Heavy Patterns

- Many records use broad `LLM`, `agentic`, `reasoning`, or `AI` framing without a visible mechanism in the title.
- Some domain papers treat reasoning as an application label rather than as the main scientific object. These stay adjacent unless the abstract makes the reasoning claim central.
- Semantic Scholar high-recall queries brought in useful breadth but also noise; the `noise` label should not be treated as a permanent exclusion until abstract/source checks are complete.

## Emerging Directions

- Multimodal and spatial reasoning is the largest visible cluster, suggesting current reasoning claims are expanding beyond text-only CoT.
- Agentic reasoning is shifting toward orchestration, workflow control, social/strategic evaluation, and multi-agent coordination.
- Evaluation/benchmark papers are abundant, which suggests the field is still negotiating what counts as reasoning progress.
- Knowledge grounding, retrieval, graph, and evidence language indicate pressure to make reasoning auditable rather than merely fluent.
- Training, distillation, and RL records suggest interest in cheaper or more internalized reasoning, but those claims require method-level inspection.
- Test-time scaling/search/verification exists but is smaller than the broad multimodal/agent/evaluation wave in this run.

## Representative Examples Per Cluster

### Multimodal, visual, video, and spatial reasoning
- [CIVIC: End-to-End Sequence Compactness for Efficient Vision-Language Models](https://www.semanticscholar.org/paper/e961c3aa2bd1786693673f6e6fa24773d5706285) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [SSR3D-LLM: Structured Spatial Reasoning via Latent Steps for Fine-Grained Grounding in Unified 3D-LLMs](https://www.semanticscholar.org/paper/a6b0401576ed2adf7d04e198bdcea821c489b393) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [Agentic Active Omni-Modal Perception for Multi-Hop Audio-Visual Reasoning](https://www.semanticscholar.org/paper/9132a72a15810082f6f801203cba8c96618d2ae6) (2026-05-27, Semantic Scholar, central, title_and_abstract)

### Agentic planning, orchestration, and multi-agent reasoning
- [DisasterBench: Benchmarking LLM Planning under Typed Tool Interface Constraints](https://www.semanticscholar.org/paper/fe47a34fac8bc24a2a2c7dde1842099f956c567a) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [Knowing When to Ask: Segment-Level Credit Assignment for LLM Tool Use](https://www.semanticscholar.org/paper/f7cb7975b8a4a5338b46f800a2abd7d17c8d4e4f) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [Beyond One Path: Evaluating and Enhancing Divergent Thinking in Interactive LLM Agents](https://www.semanticscholar.org/paper/cc2b68daeea094da1f2dbb60b666859bf9e86e1c) (2026-05-27, Semantic Scholar, central, title_and_abstract)

### General LLM reasoning frameworks and methods
- [Confidence-Orchestrated Self-Evolution against Uncertain LLM Feedback](https://www.semanticscholar.org/paper/de2004da6d47f1fe8f2bc7f9cd22130745d170cf) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [Robust and Efficient Guardrails with Latent Reasoning](https://www.semanticscholar.org/paper/be7107e257c82eb21b5e6914834fd2da5c204c15) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [Thinking as Compression: Your Reasoning Model is Secretly a Context Compressor](https://www.semanticscholar.org/paper/a1c0fe6fb340f29768f458c54e51e00ffeb845c5) (2026-05-27, Semantic Scholar, central, title_and_abstract)

### Evaluation, benchmarks, and question answering
- [BenGER: Benchmarking LLM Systems on Subsumption-Based Legal Reasoning in German Law](https://www.semanticscholar.org/paper/a225e97969bb89b720f8772907a288bbd3a188bb) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [Interpretability-Guided Layer Selection over Subspace Projection: SAEs as Stethoscopes, Not Scalpels, for Raw Task Vector Model Editing](https://www.semanticscholar.org/paper/8a61d43e49e5f851d1d1014d2c34f6eaa476e6bd) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [VibeSearchBench: Benchmarking Long-horizon Proactive Search in the Wild](https://www.semanticscholar.org/paper/844dad0df248963d61fbf088457e1fa3bed77a12) (2026-05-27, Semantic Scholar, central, title_and_abstract)

### Knowledge, retrieval, graph, and evidence-grounded reasoning
- [Framing Matters: Addressing Framing Sensitivity in Decision-Making through Behaviorally-Grounded Value Alignment](https://www.semanticscholar.org/paper/8e107c749fb00c55bc53f9654390367286ca2ade) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [MemTrace: Tracing and Attributing Errors in Large Language Model Memory Systems](https://www.semanticscholar.org/paper/49acf1e90f335385f6f4e5fb384ce47915cdf1c3) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [C-MIG: Multi-view Information Gain-based Retrieval-Augmented Generation for Clinical Diagnosis Reasoning](https://www.semanticscholar.org/paper/2aac7049a2ad5215047d8538058148c23c1f5ce0) (2026-05-27, Semantic Scholar, central, title_and_abstract)

### Training, distillation, and optimization for reasoning
- [Skill-Conditioned Gated Self-Distillation for LLM Reasoning](https://www.semanticscholar.org/paper/2ed4fbd882ecef5fcbba7bdd0c29e090eb681c5b) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [Joint Training of Multi-Token Prediction in Reinforcement Learning via Optimal Coefficient Calibration](https://www.semanticscholar.org/paper/1864f5713f2bdf46a4d25ddec4b754088e946cac) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [GeneralThinker: Domain-General Reasoning through Likelihood-Guided Answer-Conditioned Optimization](https://www.semanticscholar.org/paper/fe896a031a291b2b3dc9996807ccac0192c2b6cd) (2026-05-27, Semantic Scholar, central, title_and_abstract)

### Test-time scaling, search, verification, and self-correction
- [Not All Uncertainty Is Equal: How Uncertainty Granularity Shapes Human Verification in LLM-Assisted Decision Making](https://www.semanticscholar.org/paper/e067e08f749cba53dbe428a849e4bcbbe765fdfd) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [Tree of Thoughts as a Classical Heuristic Search Problem: Formal Foundations and Design Patterns](https://www.semanticscholar.org/paper/c609741942f75cabb6ef9d74e54037835e871709) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [ROSD: Reflective On-Policy Self-Distillation for Language Model Reasoning across Domains](https://www.semanticscholar.org/paper/b788e0db53914c1eb36ee9c75d71c83be0dbfa96) (2026-05-27, Semantic Scholar, central, title_and_abstract)

### Mathematical, logical, formal, and symbolic reasoning
- [The Fragility of Chain-of-Thought Monitoring Across Typologically Diverse Languages](https://www.semanticscholar.org/paper/7cf7c7ee3fb404de2bfb20cefaca36898c5c1f45) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [COFT: Counterfactual-Conformal Decoding for Fair Chain-of-Thought Reasoning in Large Language Models](https://www.semanticscholar.org/paper/89e21a3f35738912ec2a6d195f6afae81a443a79) (2026-05-28, Semantic Scholar, central, title_and_abstract)
- [Conformal Certification of Reasoning Trace Prefixes](https://www.semanticscholar.org/paper/c998a1bc768cb3414b686ebee8f11e4a332d7ff0) (2026-05-28, Semantic Scholar, central, title_and_abstract)

### Robustness, safety, faithfulness, and failure analysis
- [Patient-Facing Radiology Communication with LLMs: Calibration Deficit and the Metadata Paradox](https://www.semanticscholar.org/paper/f36bf703bf8d867ef93c65dda15c8bbfb83f7ae9) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [GRUFF: LLM Pronoun Fidelity, Reasoning, and Biases in German](https://www.semanticscholar.org/paper/bd777040c0a2e424f2d4e9bd679220c4b23419ca) (2026-05-28, Semantic Scholar, central, title_and_abstract)
- [Parameter Alignment Mitigates Catastrophic Forgetting in Multilingual Expert Language Models](https://www.semanticscholar.org/paper/54355ffb96d796a42ff71e659b50dffe9b8f058a) (2026-05-29, Semantic Scholar, central, title_and_abstract)

### Domain-specific scientific, medical, clinical, and legal reasoning
- [SafeMed-R1: Clinician-Audited Safety and Ethics Alignment for Medical Large Language Models](https://www.semanticscholar.org/paper/d501808d4d0cb79b29a2197758551ac1736262c9) (2026-05-27, Semantic Scholar, central, title_and_abstract)
- [PropLLM: Propagation-Aware Scene Reconstruction for Network Fault Diagnosis](https://www.semanticscholar.org/paper/b05652adce600168928c2ce3f44a081d225b7ae7) (2026-05-30, Semantic Scholar, central, title_and_abstract)
- [Med-HEAL: Analyzing and Mitigating Hallucinations in Medical LLMs with Hallucination-Aware In-Context Learning](https://www.semanticscholar.org/paper/f1d8b48cd17c7810e5d7e59bff4aefcb624ceb3e) (2026-05-31, Semantic Scholar, central, title_and_abstract)

### Code, tool, and program reasoning
- [Inferring Code Correctness from Specification](https://www.semanticscholar.org/paper/eb281bbee4d5aff4b4aeed145ee04712616c24d4) (2026-05-28, Semantic Scholar, central, title_and_abstract)
- [On the Road to Personalized Code Intelligence: Portraiting and Assisting Developers Based on Their In-IDE Behaviors](https://www.semanticscholar.org/paper/ff9d317b61e84e4c5bd67afa1eabee5e9d4ec421) (2026-05-28, Semantic Scholar, central, title_and_abstract)
- [AdaptGen: A Problem-Adaptive Solution Template Generation Technique for Online Programming Platforms](https://www.semanticscholar.org/paper/6cf9fefbc25d054e277f5b5325cb4286e13bff9c) (2026-06-01, Semantic Scholar, central, title_and_abstract)

## Open Questions for the Next Run

- Fetch arXiv abstracts through a slower retry path or an arXiv metadata mirror.
- Which central records remain central after checking method and benchmark details?
- How many adjacent domain papers actually evaluate LLM reasoning rather than using reasoning as generic application language?
- Which benchmark papers introduce new task structure versus repackaging existing QA/evaluation formats?
- Which test-time scaling papers implement real inference control rather than prompt-level budget hints?
- Which agentic reasoning papers include reproducible systems, code, or reliable baselines?
