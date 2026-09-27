# Dataset Setup

The datasets are intentionally **not included** in this repository.

EnerDR-Net uses:

1. APTOS 2019 Blindness Detection
2. Messidor-2
3. IDRiD

## Recommended local structure

```text
datasets/
├── Aptos-2019/
│   ├── train_images/
│   └── train.csv
├── Messidor_02/
│   └── messidor-2/
│       ├── images/
│       └── messidor_data.csv
└── IDRiD/
    ├── Images/
    │   └── Images/
    └── idrid_labels.csv
```

The supplied notebook is preserved exactly as provided and currently contains the original Windows dataset/output paths. Before running it on another machine, update only the path variables near the configuration section of the notebook.

Do not commit dataset images, preprocessing caches, or other restricted/large source data to GitHub.
