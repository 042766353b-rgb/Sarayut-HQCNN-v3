# Sarayut-HQCNN
### Hybrid Quantum-Classical Stability Framework (v0.1.0-alpha)

[![Status](https://img.shields.io/badge/status-v0.1.0--alpha-blue)]()
[![Peer Review](https://img.shields.io/badge/peer%20review-not%20yet-orange)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()

---

## ⚠️ Project Status Box (as of November 2026)

| Item | Current Status |
|---|---|
| **Overall stage** | Prototype Code & Conceptual Architecture |
| **Peer-reviewed publication** | ❌ None yet |
| **arXiv preprint** | ❌ Not yet submitted |
| **Empirical results** | ⏳ Stability validation in progress |
| **License** | MIT (Open Source) |

> **Honesty statement:** This repository hosts a *prototype implementation* of a stability-aware hybrid framework. We publish our status transparently so that collaborators can assess the project accurately.

---

## Overview

**Sarayut-HQCNN** is a stability-aware hybrid optimization framework designed for quantum-classical machine learning systems. 

The framework integrates a **Stability Operator (\(\Sigma\)) regularization mechanism** to reduce sensitivity to parameter perturbations, improve robustness under noise conditions, and encourage flat minima in the loss landscape.

---

## Core Concept & Mathematical Formulation

For a parameterized hybrid model with trainable parameters \(\theta\) (e.g., VQC rotation angles and classical weights), the Stability Operator is defined as:

\[
 \Sigma(\theta) = \mathbb{E}\left[ (f(\theta + \epsilon) - f(\theta))^2 \right] 
\]

Where:
- \(\theta\) = trainable parameters (classical and quantum)
- \(\epsilon\) = small perturbation noise (e.g., Gaussian noise simulating hardware decoherence)
- \(f(\cdot)\) = model output function

The total loss is defined as:

\[
 \mathcal{L}_{total} = \mathcal{L}_{task} + \lambda \Sigma(\theta) 
\]

This encourages flat minima, which is hypothesized to improve robustness against NISQ-era quantum noise and classical data distribution shifts.

---

## Features

-   **Stability-aware training loop:** Integrates \(\Sigma(\theta)\) seamlessly.
-   **JSON state serialization:** Save and load model parameters and stability metrics.
-   **LaTeX report generation:** Automatically generate tables for IEEE publication.
-   **Modular class-based architecture:** Easy to extend with VQC layers.
-   **Compatible with hybrid quantum pipelines:** (e.g., PennyLane integration planned).

---

## Installation

Requires:
-   Python 3.9+
-   PyTorch

Optional: 
-   PennyLane (for quantum circuit integration)

```bash
# Clone the repository
git clone https://github.com/your-org/sarayut-hqcnn.git
cd sarayut-hqcnn
pip install -r requirements.txt
