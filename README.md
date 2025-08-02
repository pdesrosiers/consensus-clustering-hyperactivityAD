# Consensus Clustering for Chronic Neuronal Hyperactivity Proteomics

This repository contains the Python code used for the consensus clustering analyses described in the following study, accepted in *iScience* (2025):

**Chronic optogenetic activation of hippocampal CA1 neurons triggers Alzheimer's disease-like proteomic remodeling**  
Iason Keramidis, Martina Samiotaki, Romain Sansonetti, Johanna Alonso, Patrick Desrosiers, Katerina Papanikolopoulou, Yves De Koninck  
*iScience*, 2025

---

## Purpose

To assess the similarity between proteomic profiles resulting from sustained neuronal hyperactivity in wild-type mice and those observed in Alzheimer’s disease pathology using a robust, noise-resilient clustering method.

This code performs:
- Bootstrap-based consensus clustering
- Gaussian white noise perturbation
- Rank-based cluster validation (stable, nuclear, and entropy ranks)

---
## Biological Context
The study explores how sustained optogenetic activation in the hippocampus affects protein expression:

- WT+SSFO mice showed AD-like proteomic signatures
- 5xFAD+tdTom mice clustered with WT+SSFO, revealing early convergence in disrupted proteostasis
- Results support neuronal hyperactivity as a causal contributor to AD-like remodeling

See the full paper in iScience (2025) for details.

---
## Method Summary
Consensus clustering was implemented as follows:

- Input: Protein expression matrix across mice and experimental groups
- Resampling: Bootstrap samples of proteins
- Noise model: Gaussian noise added to perturb input matrix
- Clustering: Hierarchical clustering per iteration
- Aggregation: Consensus matrix computed across all iterations
- Validation: Stability and effective rank measures (stable rank, nuclear rank, entropy rank)
- Robust clustering was confirmed by a plateau in effective rank metrics and consistent grouping of WT+SSFO and 5xFAD+tdTom mice across statistical thresholds.

---

## Citation
If you use this code in your work, please cite the original study:

> Keramidis I., Samiotaki M., Sansonetti R., Alonso J., Desrosiers P., Papanikolopoulou K., De Koninck Y. (2025). 
> Chronic optogenetic activation of hippocampal CA1 neurons triggers Alzheimer's disease-like proteomic remodeling. 
> iScience. (Accepted)

---

## Author
Developed and maintained by:

**Patrick Desrosiers**
CERVO Brain Research Centre & Université Laval\cr
patrick.desrosiers@cervo.ulaval.ca