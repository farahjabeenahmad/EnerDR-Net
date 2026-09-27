# EnerDR-Net Experimental Configuration

This document summarizes the reproducibility-critical settings present in the supplied notebook. The notebook itself remains the authoritative implementation.

## Task

Five-class diabetic retinopathy grading from retinal fundus images.

- Number of classes: 5
- Input image size: 320 x 320

## Datasets

- APTOS 2019: development dataset
- Messidor-2: external evaluation
- IDRiD: external evaluation

## Reproducibility

- Development split seed: `2026`
- Final experimental seeds: `[17, 29, 42, 73, 101]`

## Main training settings

| Setting | Value |
|---|---:|
| Number of particles | 24 |
| Particle dimension | 64 |
| Flow steps | 3 |
| Batch size | 4 |
| Gradient accumulation steps | 4 |
| Epochs | 60 |
| Patience | 12 |
| Learning rate | 2e-4 |
| Weight decay | 1e-4 |
| Focal gamma | 1.5 |
| Maximum flow step | 0.08 |
| Flow kappa | 0.02 |
| Armijo constant | 0.10 |
| Backtracking factor | 0.50 |
| Maximum backtracks | 5 |
| Active particle threshold | 0.50 |

## Experiment switches

The notebook contains independent switches for major experiment groups, including:

- Full experiment
- Ablations
- Baselines
- Interpretability
- Paper analyses
- Efficiency profiling
- Sensitivity analysis

These switches allow expensive experiment groups to be run separately without changing their scientific definitions.

## Baseline architectures

The notebook imports torchvision model implementations used for baseline comparisons, including the project baseline experiment pipeline.

## Important note

The GitHub package does not rewrite model architecture, training logic, hyperparameters, dataset split logic, or experiment definitions. Only repository-level documentation and supporting files have been added.
