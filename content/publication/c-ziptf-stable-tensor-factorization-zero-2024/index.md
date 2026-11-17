---
title: "C-ziptf: stable tensor factorization for zero-inflated multi-dimensional genomics data"
date: 2024-10-05
authors:
  - "Daniel Chafamo"
  - "Vignesh Shanmugam"
  - "Neriman Tokcan"
publication_types: ["journal_article"]
publication: "BMC Bioinformatics, 25(1), 323"
journal: "BMC Bioinformatics"
doi: "10.1186/s12859-024-05886-4"
abstract: "In the past two decades, genomics has advanced significantly, with single-cell RNA-sequencing (scRNA-seq) marking a pivotal milestone. ScRNA-seq provides unparalleled insights into cellular diversity and has spurred diverse studies across multiple conditions and samples, resulting in an influx of complex multidimensional genomics data. This highlights the need for robust methodologies capable of handling the complexity and multidimensionality of such genomics data. Furthermore, single-cell data grapples with sparsity due to issues like low capture efficiency and dropout effects. Tensor factorizations (TF) have emerged as powerful tools to unravel the complex patterns from multi-dimensional genomics data. Classic TF methods, based on maximum likelihood estimation, struggle with zero-inflated count data, while the inherent stochasticity in TFs further complicates result interpretation and reproducibility. Our paper introduces Zero Inflated Poisson Tensor Factorization (ZIPTF), a novel method for high-dimensional zero-inflated count data factorization. We also present Consensus-ZIPTF (C-ZIPTF), merging ZIPTF with a consensus-based approach to address stochasticity. We evaluate our proposed methods on synthetic zero-inflated count data, simulated scRNA-seq data, and real multi-sample multi-condition scRNA-seq datasets. ZIPTF consistently outperforms baseline matrix and tensor factorization methods, displaying enhanced reconstruction accuracy for zero-inflated data. When dealing with high probabilities of excess zeros, ZIPTF achieves up to 2.4 ×  better accuracy. Moreover, C-ZIPTF notably enhances the factorization's consistency. When tested on synthetic and real scRNA-seq data, ZIPTF and C-ZIPTF consistently uncover known and biologically meaningful gene expression programs. Access our data and code at: https://github.com/klarman-cell-observatory/scBTF and https://github.com/klarman-cell-observatory/scbtf_experiments ."
author_notes: "Vignesh Shanmugam, Daniel Chafamo and Nergiz Tokcan contributed equally."
links:
  - name: "Publisher's Version"
    url: "https://doi.org/10.1186/s12859-024-05886-4"
  - name: "Free Full Text (PMC)"
    url: "https://pmc.ncbi.nlm.nih.gov/articles/PMC11456250/"
  - name: "PubMed"
    url: "https://pubmed.ncbi.nlm.nih.gov/39369208/"
tags: ["spatial-genomics", "spatial transcriptomics", "computational pathology"]
featured: true
image_credit: "Figure from BMC Bioinformatics"
thumbnail_kind: "figure"
---
