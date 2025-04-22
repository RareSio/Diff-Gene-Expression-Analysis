# Differential Gene Expression Analysis in Microarrays

This repository contains the practical case developed for the Advanced Statistics course of the Master’s program. The project focuses on the analysis of differential gene expression using microarray data, with special emphasis on identifying differentially methylated promoter regions relevant to cancer, specifically in mouse hepatocellular carcinoma.

---

## Project Overview

The main objective of this practical case is to analyze microarray data to identify differentially methylated promoter regions and genes with altered expression associated with cancer. The study involves three groups of mice: controls, spontaneous (developing hepatocellular carcinoma naturally), and a group treated with Ginkgo biloba extract (GBE), a traditional Chinese medicine with antioxidant and anticancer properties.

### Microarray Platforms Used

- **Roche NimbleGen® Mouse DNA Methylation Microarray:** Used to identify differentially methylated promoters.
- **Affymetrix Mouse Genome 430 2.0 GeneChip Arrays:** Used to measure gene expression in the control, spontaneous, and treatment groups.

---

## Data Import and Structure

- Data is imported using the `affy` package from Bioconductor and stored in an object named `gse132575`.
- The main data object is of S4 class `AffyBatch`, which contains slots for assay data, phenotype data, and feature data.

---

## Main Steps and Analyses

1. **Data Exploration**
   - Inspection of object class, slots, and contents (e.g., phenotype and assay data).
   - Extraction of sample names and intensity measurements.

2. **Probe and Feature Analysis**
   - Determination of the number of probe pairs and probe sets.
   - Implementation of a custom R function to determine whether a given position corresponds to a PM (Perfect Match) or MM (Mismatch) probe.

3. **Gene Annotation**
   - Mapping probe set identifiers to gene symbols and Entrez IDs using Bioconductor annotation packages.

4. **Preprocessing**
   - Background correction and quantile normalization of PM probes.
   - Preprocessing with `rma()` and comparison with the `expresso()` function.

5. **Differential Expression Analysis**
   - MA plots and volcano plots to visualize differential expression.
   - Use of Student’s t-test and moderated t-statistics (empirical Bayes) with the `limma` package.
   - Multiple testing correction using methods such as Bonferroni, Sidak, Holm, Hochberg, Benjamini-Hochberg, and Benjamini-Yekutieli.

6. **Gene Selection and Biological Interpretation**
   - Selection of significantly differentially expressed genes using adjusted p-values.
   - Comparison of identified genes with those reported in the reference article (Kovi et al., 2019).
   - Biological interpretation of key genes such as Tspan8, Lrtm1, and B4galt6.

---

## References

- Kovi et al. (2019), [Original article associated with the dataset]
- Bioconductor documentation for relevant packages

---

**Author:** Andrea Santisteban Veiga  
**Course:** Advanced Statistics (Master’s level)  
**Date:** April 2023
