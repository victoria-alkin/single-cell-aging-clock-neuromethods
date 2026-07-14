# SVZ single-cell aging-clock demo input data

This folder contains a Python-readable subset of mouse subventricular zone single-cell RNA-seq aging data for the NeuroMethods single-cell aging clock demo notebook.

The subset includes:

- Aging cohort cells only
- Two cell types: Oligodendro and Microglia
- Raw RNA count data
- All genes present in the RNA assay

## Files

- `cell_metadata.csv`: cell-level metadata, including cell ID, mouse/sample ID, age in months, batch, cell type, RNA count totals, detected feature counts, and UMAP coordinates.
- `cells.csv`: cell IDs in the same order as the columns of the count matrix.
- `genes.csv`: gene IDs and gene names in the same order as the rows of the count matrix.
- `rna_counts_all_genes.npz`: sparse raw RNA count matrix with genes as rows and cells as columns.

## Use in the notebook

The demo notebook loads these raw counts, creates an AnnData object, visualizes cells using existing UMAP coordinates, creates BootstrapCells, normalizes BootstrapCell count profiles with Scanpy, trains cell-type-specific LASSO aging clocks, evaluates predictions, and inspects selected model genes.

This dataset is included for demonstration and teaching purposes.
