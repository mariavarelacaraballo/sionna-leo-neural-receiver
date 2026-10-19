# Learning log

Short notes on what I learn at each step — concepts, surprises, and mistakes.

## 2026-10-19 — Setup & Sionna Part 1

- Sionna 2.x runs on PyTorch; older examples online use the TensorFlow API and are outdated.
- **Batching:** the first tensor dimension holds independent frames simulated in parallel (Monte Carlo on the GPU).
- **LLR convention in Sionna:** LLR = ln(P(b=1) / P(b=0)), so LLR > 0 → bit 1.
- `ebnodb2no`: with unit-energy constellations, N0 = 1 / (k · r · Eb/N0).
- Sanity check: simulated uncoded QPSK BER matches theory, Q(√(2Eb/N0)).
