# Consensus Clustering for Chronic Neuronal Hyperactivity Proteomics

This repository contains the Python code used for the consensus clustering analyses described in the following study, accepted in *iScience* (2025):

**Chronic optogenetic activation of hippocampal CA1 neurons triggers Alzheimer's disease-like proteomic remodeling**  
Iason Keramidis, Martina Samiotaki, Romain Sansonetti, Johanna Alonso, Patrick Desrosiers, Katerina Papanikolopoulou, Yves De Koninck  
*iScience*, 2025


## Purpose

To assess the similarity between proteomic profiles resulting from sustained neuronal hyperactivity in wild-type mice and those observed in Alzheimer’s disease pathology using a robust, noise-resilient clustering method.

This code performs:

- Bootstrap-based consensus clustering
- Gaussian white noise perturbation
- Rank-based cluster validation (stable, nuclear, and entropy ranks)

## Biological Context
The study explores how sustained optogenetic activation in the hippocampus affects protein expression:

- WT+SSFO mice showed AD-like proteomic signatures
- 5xFAD+tdTom mice clustered with WT+SSFO, revealing early convergence in disrupted proteostasis
- Results support neuronal hyperactivity as a causal contributor to AD-like remodeling

See the full paper in iScience (2025) for details.

## Method Summary
Consensus clustering was implemented as follows:

- Input: Protein expression matrix across mice and experimental groups
- Resampling: Bootstrap samples of proteins
- Noise model: Gaussian noise added to perturb input matrix
- Clustering: Hierarchical clustering per iteration
- Aggregation: Consensus matrix computed across all iterations
- Validation: Stability and effective rank measures (stable rank, nuclear rank, entropy rank)
- Robust clustering was confirmed by a plateau in effective rank metrics and consistent grouping of WT+SSFO and 5xFAD+tdTom mice across statistical thresholds.

## Installation

This project uses **Python 3.12** or higher and requires several scientific computing packages.

> **Note**: If you already have Python and Jupyter Notebook set up on your machine, you may directly open and run the notebook `clustering_AD.ipynb`. However, for a cleaner and reproducible setup — especially for development or extension — we recommend using one of the installation options below.

### Option 1: Using conda (recommended)
Make sure you have `conda` installed. Then run:

```bash
conda env create -f environment.yml
conda activate consensus-clustering-hyperactivityAD
python -m ipykernel install --user --name=consensus-clustering-hyperactivityAD
```

This creates a new environment named `consensus-clustering-hyperactivityAD` with all dependencies.

### Option 2: Using `pip`
If you prefer using `pip`, you can install the dependencies manually in a `Python 3.12` environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install -r requirements.txt
python -m ipykernel install --user --name=consensus-clustering-hyperactivityAD
```

## Usage

After installation, you can launch Jupyter Notebook:

```bash
jupyter notebook
```
Then open the main notebook:

```bash
clustering_AD.ipynb
```

This notebook walks through the core analysis pipeline, including:

- Loading and preprocessing the data
- Feature selection based on ANOVA
- Clustering and consensus analysis
- Visualization of cluster maps and rank metrics

### Output directories
By default, results are saved in the following folders:

- `/results/threshold_analysis/` – Results from threshold sweep over number of genes $k$
- `/results/pvalue_threshold_analysis/` – Results from p-value based gene filtering

## Citation
If you use this code in your work, please cite the original study:

> Keramidis I., Samiotaki M., Sansonetti R., Alonso J., Desrosiers P., Papanikolopoulou K., De Koninck Y. (2025). 
> Chronic optogenetic activation of hippocampal CA1 neurons triggers Alzheimer's disease-like proteomic remodeling. 
> iScience. (Accepted)

## Acknowledgements

The author would like to acknowledge the insightful discussions with the authors of the study —  
**Iason Keramidis, Martina Samiotaki, Romain Sansonetti, Johanna Alonso, Katerina Papanikolopoulou,** and **Yves De Koninck** — who helped inspire the design of this analysis pipeline.

This work was supported by the *Weston Family Foundation Transformation Research* program, the *Canadian Institutes of Health Research (CIHR)*, the *Canada Research Chair* program, and the *Natural Sciences and Engineering Research Council of Canada (NSERC)*.


## Author
Developed and maintained by:

**Patrick Desrosiers**
CERVO Brain Research Centre & Université Laval
patrick.desrosiers@cervo.ulaval.ca