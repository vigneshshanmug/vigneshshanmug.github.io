---
title: "Cell type-specific inference of differential expression in spatial transcriptomics"
date: 2022-09-01
authors:
  - "Dylan M. Cable"
  - "Evan Murray"
  - "Vignesh Shanmugam"
  - "Simon Zhang"
  - "Luli S. Zou"
  - "Michael Diao"
  - "Haiqi Chen"
  - "Evan Z. Macosko"
  - "Rafael A. Irizarry"
  - "Fei Chen"
publication_types: ["journal_article"]
publication: "Nature Methods, 19(9), 1076–1087"
journal: "Nature Methods"
doi: "10.1038/s41592-022-01575-3"
abstract: "A central problem in spatial transcriptomics is detecting differentially expressed (DE) genes within cell types across tissue context. Challenges to learning DE include changing cell type composition across space and measurement pixels detecting transcripts from multiple cell types. Here, we introduce a statistical method, cell type-specific inference of differential expression (C-SIDE), that identifies cell type-specific DE in spatial transcriptomics, accounting for localization of other cell types. We model gene expression as an additive mixture across cell types of log-linear cell type-specific expression functions. C-SIDE's framework applies to many contexts: DE due to pathology, anatomical regions, cell-to-cell interactions and cellular microenvironment. Furthermore, C-SIDE enables statistical inference across multiple/replicates. Simulations and validation experiments on Slide-seq, MERFISH and Visium datasets demonstrate that C-SIDE accurately identifies DE with valid uncertainty quantification. Last, we apply C-SIDE to identify plaque-dependent immune activity in Alzheimer's disease and cellular interactions between tumor and immune cells. We distribute C-SIDE within the R package https://github.com/dmcable/spacexr ."
links:
  - name: "Publisher's Version"
    url: "https://doi.org/10.1038/s41592-022-01575-3"
  - name: "Free Full Text (PMC)"
    url: "https://pmc.ncbi.nlm.nih.gov/articles/PMC10463137/"
  - name: "PubMed"
    url: "https://pubmed.ncbi.nlm.nih.gov/36050488/"
tags: ["spatial-genomics", "spatial transcriptomics", "computational pathology"]
image_credit: "Figure from Nature Methods"
thumbnail_kind: "figure"
---
