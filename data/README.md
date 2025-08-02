# Data Directory

This folder contains preprocessed z-scored proteomic data used for clustering analysis in the study:

**Keramidis, I., Samiotaki, M., Sansonetti, R., Alonso, J., Desrosiers, P., Papanikolopoulou, K., & De Koninck, Y.**  
*Chronic optogenetic activation of hippocampal CA1 neurons triggers Alzheimer's disease-like proteomic remodeling*.  
*iScience*, 2025 (Accepted).

---

##  File: `5x-WT-WTSSFO zscore.xlsx`

### Description

This file contains **z-scored protein expression data** from mouse hippocampal tissue collected from three experimental groups:

| **Group**       | **Description**                                 |
|------------------|-------------------------------------------------|
| `5xFAD+TdTom`     | Transgenic Alzheimer’s model mice expressing tdTomato |
| `WT+SSFO`         | Wild-type mice subjected to chronic optogenetic stimulation (SSFO) |
| `WT+TdTom`        | Wild-type mice with tdTomato control virus |

Each column corresponds to one mouse sample; each row corresponds to one protein.

---

### Column Descriptions

| **Column Name**               | **Description** |
|------------------------------|-----------------|
| `5xFAD+TdTom`, `WT+SSFO`, `WT+TdTom`, etc. | Z-score normalized protein expression values |
| `C: ANOVA Significant`       | Indicates ANOVA statistical significance for group differences (`+` if significant) |
| `N: -Log ANOVA p value`      | Negative log10-transformed p-value from ANOVA |
| `T: Genes`                   | Gene symbols |
| `T: Protein.Ids`             | Protein identifiers (e.g., UniProt IDs or isoform labels) |

---

### Usage Notes

This dataset is used to:
- Select top proteins based on ANOVA significance
- Perform hierarchical and consensus clustering
- Assess the similarity of proteomic remodeling across experimental groups
- Visualize functional changes related to neuronal hyperactivity and AD pathology

Values are z-scored and ready for input into clustering algorithms.