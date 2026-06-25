# Ideas

## 2026-06-25 - RL Reasoning Token Budget Mismatch

- If `max_tokens` is not part of the model input and only acts as a decoding cutoff, can the model actually know the inference-time token budget?
- If RL training used a 1K token budget but inference allows 5K tokens, is this a train/inference budget mismatch? Is the policy mainly practical only in a 1K-token environment?
- If RL training used a 5K token budget but deployment allows only 1K tokens, is the policy impractical because it may depend on longer traces and get truncated?
- How much of the behavior is determined by RL training settings such as rollout max length, truncation handling, reward design, and length penalty?
