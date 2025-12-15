# Convolution-Filter
A signal-processing–oriented repository for studying and implementing convolutional filters used in modern CNNs, including wavelet-based, dilated, and multi-rate convolutions.

## Motivation

In classical signal processing, filtering, sampling, and multi-rate operations are
designed under strict theoretical principles such as the Nyquist–Shannon sampling theorem
and energy preservation (Parseval's theorem).

However, many convolutional neural network (CNN) architectures violate these principles
(e.g., strided convolution without low-pass filtering or max pooling),
yet still achieve strong empirical performance.

This repository aims to bridge this gap by reinterpreting CNN convolution operators as
**structured signal transforms**, and by analyzing when and why such violations
are acceptable—or even beneficial—for learning-based systems.

---

## Scope

This repository focuses on convolution operators that go beyond standard spatial convolution,
including but not limited to:

- Wavelet-based convolutions (e.g., Haar, multi-level wavelet transforms)
- Dilated (atrous) convolutions and their effective receptive fields
- Strided convolutions and subsampling effects
- Pooling operations from an aliasing and information-loss perspective
- Anti-aliased and low-pass filtered downsampling
- Multi-rate and multi-scale convolutional operators

Each operator is analyzed in terms of:
- Frequency response
- Energy preservation
- Aliasing behavior
- Information redistribution across channels
- Impact on representation learning

---

## Key Perspectives

This repository is built upon the following viewpoints:

- **Convolution as a signal transform**, not merely a learnable operation
- **Channels as basis coefficients** rather than independent feature maps
- **Downsampling as a multi-rate signal processing problem**
- **Energy preservation as a proxy for information preservation**
- **Learning as a mechanism that can compensate for structured distortions (e.g., aliasing)**

These perspectives help unify classical signal processing theory and modern deep learning practice.

---

## Repository Structure

```text
signal-aware-convolutions/
│
├── wavelet/
│   ├── haar/
│   ├── multilevel/
│   └── analysis/
│
├── dilation/
│   ├── atrous_conv/
│   └── receptive_field/
│
├── downsampling/
│   ├── stride_conv/
│   ├── pooling/
│   └── anti_aliasing/
│
├── analysis/
│   ├── frequency_response/
│   ├── energy_preservation/
│   └── aliasing_effects/
│
├── experiments/
│   ├── image_restoration/
│   ├── classification/
│   └── ablation_studies/
│
└── README.md
