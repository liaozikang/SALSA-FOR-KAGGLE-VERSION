# SALSA-FOR-KAGGLE-VERSION
a version can dierctly use in kaggle
This dataset is a Kaggle-compatible release of the SALSA (NeurIPS 2022) codebase, which implements a Transformer-based attack on Lattice Cryptography (LWE).

The original code was designed for large-scale Slurm clusters. This version has been adapted to run on Kaggle's single-GPU environment (T4 x2), making it easier to reproduce and experiment with the paper's findings.

### Key Modifications
- Removed Slurm dependency, forced single-GPU execution
- Fixed `inspect.getargspec` deprecation for Python 3.12+
- Fixed `torch.cuda.set_device` compatibility issues
- Converted absolute paths to relative paths for Kaggle

### Content
- `train.py`: Main training entry point
- `src/`: Core model and environment code
- `checkpoint/`: Directory for saving model checkpoints
- `notebooks/`: Analysis notebooks
- `README.md`: Detailed documentation
- `requirements.txt`: Python dependencies

### Quick Start
```python
%cd /kaggle/working/SALSA
!python train.py --N 5 --Q 251 --sigma 3 --max_epoch 10
citation
@inproceedings{wenger2022salsa,
  title={SALSA: Attacking Lattice Cryptography with Transformers},
  author={Wenger, Emily and Chen, Mingjie and Charton, Francois and Lauter, Kristin},
  booktitle={NeurIPS},
  year={2022}
}
