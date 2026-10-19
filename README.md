# Neural OFDM Receiver under LEO Doppler — with NVIDIA Sionna

> 🚧 **Work in progress** — personal project, started October 2026.

Can a neural receiver trained end-to-end outperform a classical OFDM receiver (LS/LMMSE channel estimation + equalization) on a **LEO satellite-to-ground link**, where Doppler shifts are large and change throughout the satellite pass?

This repository documents my attempt to answer that question with [NVIDIA Sionna](https://nvlabs.github.io/sionna/), from first tutorials to final BER/BLER comparisons.

## Motivation

Non-Terrestrial Networks (NTN) are part of 5G-Advanced and a core pillar of 6G. Low Earth Orbit satellites move at ~7.5 km/s, which produces Doppler shifts of tens of kHz at S/Ka-band and a Doppler rate that keeps changing during a pass. Classical receivers rely on pilot-based estimation and interpolation, which can break down when the channel varies quickly within an OFDM slot. Learned receivers are a promising alternative — this project tests where (and whether) they actually help.

## Roadmap

- [ ] **Phase 1 — Foundations:** Sionna PHY tutorials (Parts 1–4) and the OFDM neural receiver tutorial
- [ ] **Phase 2 — LEO channel:** Doppler + delay model for a satellite pass; 3GPP NTN channel (TR 38.811) if feasible
- [ ] **Phase 3 — Receivers:** classical baseline (LS / LMMSE + equalization) and a trained neural receiver
- [ ] **Phase 4 — Results:** BER/BLER vs SNR and vs Doppler; analysis of when the neural receiver wins
- [ ] **Phase 5 — Write-up:** clean results, reproducibility instructions

**Possible extensions:** joint channel + position/velocity estimation (ISAC); reinforcement learning for handover in LEO constellations.

## Repository structure

```
notebooks/   Jupyter notebooks, numbered in the order they were developed
src/         Reusable code (channel model, receivers, training loops)
results/     Saved metrics and figures
docs/        Learning log and technical notes
```

## Setup

The notebooks run on **Google Colab** (free GPU) or locally:

```bash
pip install -r requirements.txt
```

Sionna ≥ 2.0 is built on **PyTorch** (TensorFlow is no longer used). A CUDA GPU is recommended for training.

## Results

*Coming soon.*

## Learning log

I'm documenting what I learn along the way in [`docs/learning-log.md`](docs/learning-log.md).

## Author

**María Varela** — Telecommunications Engineer (Universidad de Sevilla), M2 SAR student (Advanced Radiocommunication Systems & AI) at CentraleSupélec / Université Paris-Saclay.

## License

[MIT](LICENSE)
