# PRISM---Based-FFT-J-PRISM
Alternative to FFT - early research # J-PRISM – FFT Alternative for Radar & Signal Processing

**MIT Licensed – No Extraction – For Peaceful Use**

## What This Is

A **GPU‑accelerated, prism‑based feature extraction kernel** for radar signal processing. It extracts **range, Doppler, variance, and coherence** directly from IQ data—**without a full FFT**.

It's designed for **drone de‑escalation, early warning, and sovereign defence**—faster, cheaper, and more reliable than traditional FFT-based approaches.

## Why It Matters

| FFT‑Based Approach | J‑PRISM Approach |
|--------------------|------------------|
| Computes full spectrum | Extracts only what's needed for tracking |
| Higher latency | Lower latency (GPU‑parallel) |
| Memory‑heavy | Memory‑efficient |
| Needs post‑processing | Features ready to use |
| Sensitive to noise | Coherence filter rejects noise |

**For tracking drones, you don't need the full spectrum—you need range, Doppler, and coherence. J‑PRISM gives you exactly that.**

## How It Works

The kernel runs on a GPU and extracts:

| Feature | What It Tells You |
|---------|-------------------|
| **Mean Range** | Distance to target |
| **Mean Doppler** | Velocity of target |
| **Variance** | Target size/type |
| **Coherence** | Distinguishes real targets from noise/clutter |

## Who This Is For

- **Sovereign nations** seeking independent radar capability
- **Researchers** working on drone detection and de‑escalation
- **Engineers** building open, non‑extractive defence systems
- **Quiet stewards** who build without seeking fame

## The Intent

> *“De‑escalation of drones—and children coming home to sovereign countries.”*

This is MIT‑licensed so any sovereign nation can use it freely—without extraction, without gatekeeping, without control.

## Getting Started

The kernel is CUDA‑based and expects IQ data as input. It outputs a `PrismFeature` struct for each cell.

```cpp
struct PrismFeature
{
    float meanRange;
    float meanDoppler;
    float variance;
    float coherence;
};
