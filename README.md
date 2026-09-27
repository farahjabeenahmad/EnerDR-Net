# EnerDR-Net

**EnerDR-Net: A lightweight energy-driven particle-based deep learning framework for five-class diabetic retinopathy grading with cross-dataset validation on APTOS, Messidor-2, and IDRiD.**

## Overview

EnerDR-Net is an experimental deep learning framework for ordinal diabetic retinopathy grading from retinal fundus images. The repository contains the full research notebook supplied for the project together with reproducibility and GitHub packaging files.

The experimental workflow includes:

- retinal image preprocessing;
- five-class diabetic retinopathy grading;
- energy-driven particle-based modeling;
- multi-seed training and evaluation;
- external evaluation on Messidor-2 and IDRiD;
- matched baseline experiments;
- ablation studies;
- sensitivity analysis;
- interpretability analyses;
- calibration and paper-oriented analyses;
- computational efficiency profiling; and
- experiment output/checkpoint handling.

## Repository Structure

```text
EnerDR-Net/
├── README.md
├── LICENSE
├── CITATION.cff
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── EnerDRNet.ipynb
├── configs/
│   └── paths.example.json
├── data/
│   └── README.md
├── docs/
│   └── experiment_details.md
├── assets/
└── outputs/
    ├── checkpoints/
    ├── figures/
    ├── tables/
    ├── predictions/
    └── profiles/
```

## Datasets

The project uses three retinal fundus datasets:

1. **APTOS 2019 Blindness Detection**
2. **Messidor-2**
3. **IDRiD**

Dataset files are **not distributed** with this repository. Obtain them from their authorized/official sources and configure the local paths before running the notebook.

See [`data/README.md`](data/README.md) for the recommended directory structure.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/EnerDR-Net.git
cd EnerDR-Net
```

### 2. Create an environment

Example with Python `venv`:

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Activate it on Linux/macOS:

```bash
source .venv/bin/activate
```

### 3. Install PyTorch

The original experiment environment used **PyTorch 2.7.1 with CUDA 11.8**.

For a CUDA 11.8 installation:

```bash
pip install torch==2.7.1 torchvision==0.22.1 --index-url https://download.pytorch.org/whl/cu118
```

For CPU-only or a different CUDA version, use the PyTorch installation command appropriate for your platform.

### 4. Install remaining dependencies

```bash
pip install -r requirements.txt
```

If PyTorch has already been installed with a platform-specific command, pip will normally recognize the installed compatible version.

## Path Configuration

The supplied notebook is intentionally preserved as provided. It currently contains the original Windows paths for APTOS, Messidor-2, IDRiD, and the output directory.

Before running on another machine, update the path variables in the notebook configuration section.

An example portable layout is provided in:

```text
configs/paths.example.json
```

Example paths:

```text
datasets/Aptos-2019/train_images
datasets/Aptos-2019/train.csv
datasets/Messidor_02/messidor-2/images
datasets/Messidor_02/messidor-2/messidor_data.csv
datasets/IDRiD/Images/Images
datasets/IDRiD/idrid_labels.csv
outputs
```

Changing filesystem paths does not require changing the model architecture or experimental protocol.

## Running the Notebook

Start Jupyter:

```bash
jupyter notebook
```

Then open:

```text
notebooks/EnerDRNet.ipynb
```

The notebook includes switches for expensive experiment groups so that different sections can be run separately.

## Reproducibility

The supplied notebook contains the following primary randomization settings:

```python
SPLIT_SEED = 2026
FINAL_SEEDS = [17, 29, 42, 73, 101]
```

Key configuration values include:

```python
NUM_CLASSES = 5
IMAGE_SIZE = 320
NUM_PARTICLES = 24
PARTICLE_DIM = 64
FLOW_STEPS = 3
BATCH_SIZE = 4
ACCUM_STEPS = 4
EPOCHS = 60
PATIENCE = 12
LR = 2e-4
WEIGHT_DECAY = 1e-4
FOCAL_GAMMA = 1.5
FLOW_MAX_STEP = 0.08
FLOW_KAPPA = 0.02
ARMIJO_C = 0.10
BACKTRACK_FACTOR = 0.50
MAX_BACKTRACKS = 5
ACTIVE_PARTICLE_THRESHOLD = 0.50
```

For a compact experimental summary, see [`docs/experiment_details.md`](docs/experiment_details.md).

## Experiment Controls

The notebook provides independent switches such as:

```python
RUN_FULL_EXPERIMENT = True
RUN_ABLATIONS = True
RUN_BASELINES = True
RUN_INTERPRETABILITY = True
RUN_PAPER_ANALYSES = True
RUN_EFFICIENCY_PROFILE = True
RUN_SENSITIVITY = True
```

This allows computationally expensive experiment groups to be executed separately.

## Generated Files

Large/generated files are intentionally excluded from Git version control, including:

- datasets;
- preprocessing caches;
- `.pt`, `.pth`, and `.ckpt` model files;
- temporary logs;
- prediction dumps;
- profiler traces; and
- generated experiment artifacts.

The repository provides empty output directories for organization:

```text
outputs/checkpoints/
outputs/figures/
outputs/tables/
outputs/predictions/
outputs/profiles/
```

## Citation

If you use this code in academic work, cite the corresponding EnerDR-Net publication when it becomes available.

Before publishing the GitHub repository, update [`CITATION.cff`](CITATION.cff) with the final author list, repository URL, paper title, DOI, journal, and publication details.

## License

This package currently includes an MIT License template. Review the licensing terms before making the repository public, particularly if the associated manuscript or institutional code has different distribution requirements.

## Repository Topics

Suggested GitHub topics:

`diabetic-retinopathy` `deep-learning` `medical-imaging` `fundus-images` `pytorch` `computer-vision` `ordinal-classification` `retinal-imaging` `healthcare-ai` `explainable-ai` `image-classification` `enerdr-net`
