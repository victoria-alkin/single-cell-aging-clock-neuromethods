# SVZ single-cell aging-clock demo input data

This folder contains a Python-readable subset of the mouse SVZ single-cell RNA-seq aging dataset from Buckley/Sun et al., Nature Aging 2023.

The subset includes:
- Aging cohort cells only
- Two cell types: Oligodendro and Microglia
- Raw RNA count data
- All genes present in the RNA assay

Files:
- cell_metadata.csv.gz: cell-level metadata, including mouse/sample ID, age in months, batch, cell type, nCount_RNA, and nFeature_RNA.
- cells.csv.gz: cell IDs in the same order as the columns of the count matrix.
- genes.csv.gz: gene IDs/names in the same order as the rows of the count matrix.
- rna_counts_all_genes.mtx.gz: sparse Matrix Market count matrix with genes as rows and cells as columns.

The interactive notebook will load these raw counts, perform simple library-size normalization and log transformation, create BootstrapCells, train a simplified aging clock, and visualize predictions.
