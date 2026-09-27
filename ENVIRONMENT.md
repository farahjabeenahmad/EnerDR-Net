# Reference Environment

The supplied research notebook was developed with the following reference deep-learning environment:

- PyTorch: 2.7.1
- CUDA toolkit/runtime target: 11.8
- torchvision: 0.22.1

GPU availability and exact driver requirements depend on the machine used to reproduce the experiments.

Install the CUDA 11.8 PyTorch wheels with:

```bash
pip install torch==2.7.1 torchvision==0.22.1 --index-url https://download.pytorch.org/whl/cu118
```

Then install the remaining packages with:

```bash
pip install -r requirements.txt
```
