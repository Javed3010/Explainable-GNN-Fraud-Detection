# Reproducibility and execution

1. Use Python with a PyTorch/PyG-compatible environment.
2. Install `requirements.txt`; if PyG installation fails, follow the official platform-specific PyG installation instructions.
3. Keep the three Elliptic CSVs in `data/elliptic_bitcoin_dataset/`.
4. Launch Jupyter from the repository root.
5. Start with `Baseline-ML.ipynb`, then `Baseline-GNNs.ipynb`, `Ellptic_TAGCN.ipynb`, and `AblationStudy.ipynb`. Plot notebooks can be run after relevant model results are available.

## Known portability caveats

- Some cells reference `/home/sraoham1/Illicit` or Google Colab; remove or adapt these paths.
- Some notebooks use `!pip install` magic commands.
- GPU support, library versions, random seeds, and runtime vary by environment.
- Notebook execution and metric reproduction have **not** been verified for this release.
- Check split methodology and class mappings before comparing metrics.
