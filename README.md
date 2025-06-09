# m6a-nurd-aml-resistance

This repository contains all analysis code associated with the manuscript:

**"m6A and NuRD complexes regulate monocytic differentiation and resistance to BCL2/BCL2L1 inhibitors in AML"**  
*Brim-Edwards et al., 2025*

We present computational workflows supporting CRISPR screen analysis, RNA-seq differential expression, pathway activity inference via PCA, and correlation of epigenetic features with drug response in AML. Code is provided for all primary and supplemental figures.

---

## Summary

Loss of the m⁶A methyltransferase adaptor **RBM15** and NuRD complex interactor **ZMYND8** induces resistance to BCL2 inhibitors (venetoclax and AZD4320) in AML through alterations in apoptotic balance and promotion of monocytic differentiation. In patient data, reduced activity of the m⁶A and NuRD complexes correlates with more differentiated disease states and reduced sensitivity to BCL2-family inhibitors. 

---

## Repository Contents

- `Combined Paper Code.Rmd` – all code for primary figures (1–6)
- `AZD4320 Paper Supplemental Code.Rmd` – supplemental analyses and validation results
- Scripts include:
  - CRISPR screen processing and tiering
  - RNA-seq preprocessing and DESeq2 analysis
  - PCA of m6A and NuRD pathway members (RNA and proteomics)
  - Drug response correlation analyses
  - GSEA using MSigDB and PanglaoDB annotations

---

## Software Requirements

The analysis was conducted in **R (≥ 4.2)** and uses the following R packages:

**Core analysis**
- `tidyverse`
- `data.table`
- `DESeq2`, `edgeR`
- `AnnotationDbi`, `org.Hs.eg.db`
- `ComplexHeatmap`, `clusterProfiler`, `enrichplot`, `msigdbr`
- `factoextra`, `ggrepel`, `ggsignif`, `ggtext`, `scales`

**Reproducibility and workflow**
- `here`
- `janitor`
- `broom`, `patchwork`, `cowplot`, `ggbeeswarm`
- `future`, `furrr`, `tictoc`, `purrr`, `conflicted`

**Optional aesthetics**
- `ggprism`
- `circlize`
- `readxl`
- `scattermore`

You can install all required packages using:
```r
install.packages(c("tidyverse", "data.table", "here", "janitor", "broom", "patchwork", "cowplot", 
                   "ggbeeswarm", "ggrepel", "ggsignif", "ggtext", "scales", "ggprism", "purrr",
                   "future", "furrr", "tictoc", "conflicted", "readxl", "scattermore"))
BiocManager::install(c("DESeq2", "edgeR", "AnnotationDbi", "org.Hs.eg.db", "ComplexHeatmap",
                       "clusterProfiler", "enrichplot", "msigdbr", "factoextra"))
```

If an `renv.lock` file is provided in future versions, you may also use `renv::restore()`.

---

## Data Availability

- **CRISPR screen raw data**: [GEO accession GSE294240]
- **Drug response and expression data**: Publicly available from the [BEAT AML dataset]
- **Supplementary results and intermediate datasets**: Provided in the supplement to the published manuscript

---

## Citation

If you use this repository or its components, please cite:

> Brim-Edwards J, Morris K, Morrow Q, et al. m6A and NuRD complexes regulate monocytic differentiation and resistance to BCL2/BCL2L1 inhibitors in AML. *Haematologica*. 2025.

---

## Contact

For questions, please contact [Jackson Brim-Edwards](brimedwa@ohsu.edu) or open an issue on this repository.
