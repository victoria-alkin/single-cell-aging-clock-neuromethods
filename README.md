# Single-Cell Aging Clock NeuroMethods Demo

This repository contains a Jupyter notebook demonstrating how to build a simple single-cell transcriptomic aging clock using Python.

The notebook accompanies a NeuroMethods chapter on biological age prediction using single-cell omics data. It uses a subset of mouse subventricular zone single-cell RNA-seq data from Buckley et al., 2022 to demonstrate the major steps of building and evaluating cell-type-specific transcriptomic aging clocks.

## Repository structure

```text
single-cell-aging-clock-neuromethods/
|-- README.md
|-- environment.yml
|-- requirements.txt
|-- notebooks/
|   |-- 01_single_cell_aging_clock_demo.ipynb
|-- data/
|   |-- svz_oligodendro_microglia_counts/
|       |-- README.md
|       |-- cell_metadata.csv
|       |-- cells.csv
|       |-- genes.csv
|       |-- rna_counts_all_genes.npz
|-- figures/
```

## What the notebook demonstrates

The notebook walks through a simplified single-cell transcriptomic aging clock workflow, including how to:

1. Load cell-level metadata and raw count data.
2. Inspect the modeling input and perform basic QC checks.
3. Visualize cells using UMAP coordinates.
4. Create BootstrapCells by sampling cells from the same mouse and cell type.
5. Normalize BootstrapCell count profiles using Scanpy-style normalization and log transformation.
6. Select highly variable genes with Scanpy.
7. Train cell-type-specific aging clocks using a StandardScaler + LASSO model.
8. Evaluate predicted age against chronological age using held-out batches and mouse-level summaries.
9. Build final LASSO models and inspect selected genes.
The notebook is intended as a teaching example rather than a fully optimized aging-clock pipeline.

## Setup Option 1: Conda environment

If you use Conda or Miniforge, create the environment from `environment.yml`:

```bash
conda env create -f environment.yml
conda activate sc-aging-clock-neuromethods
python -m ipykernel install --user --name sc-aging-clock-neuromethods --display-name "Python 3 (sc-aging-clock-neuromethods)"
```

Then launch JupyterLab from the repository root:

```bash
jupyter lab
```

## Setup option 2: Python virtual environment

If you prefer `venv` and `pip`, create and activate a virtual environment from the repository root.

On Windows PowerShell:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements.txt
python -m ipykernel install --user --name single-cell-aging-clock --display-name "Python (single-cell aging clock)"
jupyter lab
```

On macOS or Linux:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements.txt
python -m ipykernel install --user --name single-cell-aging-clock --display-name "Python (single-cell aging clock)"
jupyter lab
```

## Running the notebook

Launch JupyterLab from the repository root, then open:

```text
notebooks/01_single_cell_aging_clock_demo.ipynb
```

Select the kernel corresponding to the environment you created, then run the notebook cells from top to bottom.

The notebook expects the data folder to be located at:

```text
data/svz_oligodendro_microglia_counts/
```