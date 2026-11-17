---
title: "Use of Deep Learning to Develop and Analyze Computational Hematoxylin and Eosin Staining of Prostate Core Biopsy Images for Tumor Diagnosis"
date: 2020-05-20
authors:
  - "Aman Rana"
  - "Alarice Lowe"
  - "Marie Lithgow"
  - "Katharine Horback"
  - "Tyler Janovitz"
  - "Annacarolina Da Silva"
  - "Harrison Tsai"
  - "Vignesh Shanmugam"
  - "Akram Bayat"
  - "Pratik Shah"
publication_types: ["journal_article"]
publication: "JAMA Network Open, 3(5), e205111"
journal: "JAMA Network Open"
doi: "10.1001/jamanetworkopen.2020.5111"
abstract: "Histopathological diagnoses of tumors from tissue biopsy after hematoxylin and eosin (H&E) dye staining is the criterion standard for oncological care, but H&E staining requires trained operators, dyes and reagents, and precious tissue samples that cannot be reused. To use deep learning algorithms to develop models that perform accurate computational H&E staining of native nonstained prostate core biopsy images and to develop methods for interpretation of H&E staining deep learning models and analysis of computationally stained images by computer vision and clinical approaches. This cross-sectional study used hundreds of thousands of native nonstained RGB (red, green, and blue channel) whole slide image (WSI) patches of prostate core tissue biopsies obtained from excess tissue material from prostate core biopsies performed in the course of routine clinical care between January 7, 2014, and January 7, 2017, at Brigham and Women's Hospital, Boston, Massachusetts. Biopsies were registered with their H&E-stained versions. Conditional generative adversarial neural networks (cGANs) that automate conversion of native nonstained RGB WSI to computational H&E-stained images were then trained. Deidentified whole slide images of prostate core biopsy and medical record data were transferred to Massachusetts Institute of Technology, Cambridge, for computational research. Results were shared with physicians for clinical evaluations. Data were analyzed from July 2018 to February 2019. Methods for detailed computer vision image analytics, visualization of trained cGAN model outputs, and clinical evaluation of virtually stained images were developed. The main outcome was interpretable deep learning models and computational H&E-stained images that achieved high performance in these metrics. Among 38 patients who provided samples, single core biopsy images were extracted from each whole slide, resulting in 102 individual nonstained and H&E dye-stained image pairs that were compared with matched computationally stained and unstained images. Calculations showed high similarities between computationally and H&E dye-stained images, with a mean (SD) structural similarity index (SSIM) of 0.902 (0.026), Pearson correlation coefficient (PCC) of 0.962 (0.096), and peak signal to noise ratio (PSNR) of 22.821 (1.232) dB. A second cGAN performed accurate computational destaining of H&E-stained images back to their native nonstained form, with a mean (SD) SSIM of 0.900 (0.030), PCC of 0.963 (0.011), and PSNR of 25.646 (1.943) dB compared with native nonstained images. A single blind prospective study computed approximately 95% pixel-by-pixel overlap among prostate tumor annotations provided by 5 board certified pathologists on computationally stained images, compared with those on H&E dye-stained images. This study also used the first visualization and explanation of neural network kernel activation maps during H&E staining and destaining of RGB images by cGANs. High similarities between kernel activation maps of computationally and H&E-stained images (mean-squared errors <0.0005) provide additional mathematical and mechanistic validation of the staining system. These findings suggest that computational H&E staining of native unlabeled RGB images of prostate core biopsy could reproduce Gleason grade tumor signatures that were easily assessed and validated by clinicians. Methods for benchmarking, visualization, and clinical validation of deep learning models and virtually H&E-stained images communicated in this study have wide applications in clinical informatics and oncology research. Clinical researchers may use these systems for early indications of possible abnormalities in native nonstained tissue biopsies prior to histopathological workflows."
links:
  - name: "Publisher's Version"
    url: "https://doi.org/10.1001/jamanetworkopen.2020.5111"
  - name: "Free Full Text (PMC)"
    url: "https://pmc.ncbi.nlm.nih.gov/articles/PMC7240356/"
  - name: "PubMed"
    url: "https://pubmed.ncbi.nlm.nih.gov/32432709/"
tags: ["molecular-pathology", "computational pathology"]
image_credit: "Figure from JAMA Network Open"
thumbnail_kind: "figure"
---
