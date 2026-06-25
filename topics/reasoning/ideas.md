# Ideas

Last updated: 2026-06-25

## Token Budget Mismatch in RL Reasoning

### Core Observation

In standard autoregressive decoding, the API-side `max_tokens` cap is not necessarily part of the model input. If the cap is only a server-side truncation rule, the model samples from:

```text
p_theta(y_t | x, y_<t)
```

not from:

```text
p_theta(y_t | x, budget, y_<t)
```

So changing `max_tokens` alone should not make the first part of the generation budget-aware. With deterministic decoding and the same prompt, the trajectory should be the same until the shorter cap cuts it off.

### Hypothesis

RL with a fixed rollout cap does not teach explicit awareness of the hidden inference cap. It teaches a length prior, stopping policy, and reasoning style optimized for the rollout environment.

- If a model is RL-trained with a 1K rollout cap, it may learn to answer early and fail to exploit a 5K inference budget.
- If a model is RL-trained with a 5K rollout cap, it may learn to explore or delay the final answer too long and become impractical under a 1K deployment cap.
- Therefore, train-time budget and inference-time budget mismatch can directly affect the practical usefulness of RL reasoning policies.

### Research Questions

1. How robust are RL reasoning models to train/inference token-budget mismatch?
2. What differs between a model trained under a hidden rollout cap and one explicitly conditioned on a budget token or budget instruction?
3. Can an anytime reasoning format preserve utility under early truncation while still improving when extra tokens are available?
4. Does test-time compute scaling require explicit budget conditioning, or can mixed-budget RL induce enough implicit robustness?

### Experiment Sketch

Train or compare variants:

1. Fixed hidden cap: RL rollouts capped at 1K.
2. Fixed hidden cap: RL rollouts capped at 5K.
3. Mixed hidden caps: randomly sample caps such as 1K, 2K, 5K without telling the model.
4. Explicit budget conditioning: include instructions or tokens such as `<budget=1k>` and `<budget=5k>` in the input.
5. Anytime / answer-first traces: produce an initial answer early, then use remaining tokens for verification, search, and refinement.

Evaluate each variant under multiple inference caps: 1K, 2K, 5K, and possibly longer extrapolation budgets.

### Metrics

- Accuracy at each inference cap.
- Answer presence rate before cutoff.
- Truncation failure rate.
- Tokens-to-first-answer.
- EOS timing distribution.
- Marginal accuracy gain from extra tokens.
- Rate of post-answer correction during verification/refinement.

### Expected Pattern

- Fixed-cap RL likely overfits to the training budget.
- A 1K-trained policy may be useful in 1K deployment but may underuse 5K test-time compute.
- A 5K-trained policy may benefit from long inference but may fail under short deployment caps.
- Mixed hidden caps may improve robustness but still cannot condition perfectly on the actual hidden API cap.
- Explicit budget-conditioned RL should better adapt exploration depth and answer timing.
- Anytime or answer-first formats should reduce catastrophic truncation in short-budget settings.

### Practical Takeaway

Extra `max_tokens` is useful only if the policy knows how to convert extra tokens into search, verification, or refinement. Otherwise, the extra budget may be unused by a short-budget-trained policy, while a long-budget-trained policy may be brittle when deployed with a smaller cap.

For scalable test-time compute, the model should ideally be trained with one or more of the following:

- explicit budget conditioning,
- multiple rollout budgets,
- length-aware rewards,
- answer-first then verify/refine behavior,
- anytime reasoning objectives.

Related note: https://matthewyryang.com/e3/
