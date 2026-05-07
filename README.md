# Kalman Filter for Neural Kinematic Decoding

A complete implementation of a Kalman filter for decoding movement kinematics from neural firing rates.

## Overview

This project implements a linear Kalman filter to decode kinematic variables (position and velocity) from neural spiking activity. The system is first identified from training data, then applied recursively to test data.

## Theoretical Background

The Kalman filter operates in two steps:
1. **Prediction**: Project state forward using dynamics model
2. **Update**: Incorporate neural observations to correct prediction

The model assumes:
- Linear dynamics: `xₜ = A·xₜ₋₁ + wₜ`
- Linear observation: `zₜ = H·xₜ + vₜ`

## Implementation Details

- System identification from training data (least squares)
- Recursive filtering on test data
- R² evaluation for each kinematic variable
- Analysis of initialization effects (x₀, P₀ variations)
- Kalman gain convergence analysis

## Results

| Variable | R² Score |
|----------|----------|
| x position | 0.89 |
| y position | 0.91 |
| x velocity | 0.68 |
| y velocity | 0.63 |

Kalman gain stabilizes within 15-20 time steps.

## Technologies

- Python
- JAX (for numerical computation)
- NumPy
- SciPy
- Matplotlib



## Author

Chiara Benini
