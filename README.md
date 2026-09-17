# BAKEEN-THREE-FORK-CLUSTERING# Data-Driven Petrophysical Clustering of the Bakken–Three Forks System

This repository contains the Python code supporting the petrophysical clustering and reservoir-quality analysis presented in our study of the Bakken–Three Forks system.

The workflow applies unsupervised machine-learning methods to identify petrophysically distinct reservoir domains using core-derived reservoir properties. The analysis includes data preprocessing, principal component analysis (PCA), clustering, statistical validation, robustness testing, and engineering interpretation of the resulting clusters.

## Study Workflow

The main workflow includes:

1. Data cleaning and formation selection
2. Log10 transformation of permeability
3. Feature normalization and standardization
4. Principal Component Analysis (PCA)
5. K-means clustering
6. Hierarchical clustering
7. Gaussian Mixture Model (GMM) analysis
8. Cluster-number evaluation and sensitivity analysis
9. Cluster stability and robustness assessment
10. Well- and formation-level cluster analysis
11. Engineering validation using reservoir-quality proxies
12. Statistical comparison of the identified petrophysical domains

## Dataset

The analysis considers intervals from:

- Middle Bakken
- Upper Three Forks
- Middle Three Forks

The original dataset contains 1,422 records. After formation selection, 1,034 records remained, and complete-case filtering resulted in 623 observations from 9 wells.

The principal variables used for clustering are derived from:

- Core porosity
- Core permeability
- Formation thickness
- Core water saturation

Permeability is transformed using log10 prior to clustering.

## Clustering Methodology

The petrophysical variables are normalized and subsequently standardized before multivariate analysis.

PCA is used primarily for dimensionality reduction, visualization, and interpretation of variable loadings. Clustering is performed on the standardized petrophysical feature space rather than directly on the PCA scores.

The repository evaluates multiple unsupervised approaches, including:

- K-means clustering
- Agglomerative hierarchical clustering
- Gaussian Mixture Models (GMM)

The principal K-means interpretation uses **k = 3** petrophysical clusters.

## Physical and Statistical Validation

The identified clusters are evaluated using two engineering screening proxies:

- Transmissibility proxy: `kh`
- Effective pore-volume proxy: `φh(1-Sw)`

Differences between clusters are assessed using non-parametric statistical testing, including the Kruskal–Wallis test and Dunn's post-hoc comparisons.

Additional robustness analyses examine the effects of normalization strategy, outlier removal, random initialization, and clustering stability.

## Repository Contents

`bakken_three_forks_clustering.py`  
Python script containing the complete data-processing, clustering, validation, statistical-analysis, and visualization workflow.

`README.md`  
Description of the repository, methodology, and reproducibility information.

## Requirements

The analysis was developed in Python and uses commonly available scientific-computing and machine-learning libraries, including:

- pandas
- numpy
- scipy
- scikit-learn
- matplotlib
- seaborn
- scikit-posthocs

## Running the Analysis

The original workflow was developed and executed in Google Colab.

To reproduce the analysis, place the required dataset in the working directory and update the dataset path in the script if necessary.

The analysis can then be executed sequentially in a compatible Python or Google Colab environment.

## Data Availability

The dataset used in this study is not included in this repository unless explicitly provided in the `data` directory. Users should refer to the associated publication for information regarding the source and availability of the underlying data.

## Citation

If you use this code or methodology, please cite the associated publication:

> [Authors]. [Article title]. [Journal], [Year]. [DOI]

The complete citation and DOI will be added following publication.

## License

Please refer to the `LICENSE` file for the terms governing reuse of the code in this repository.

## Contact

For questions regarding the methodology or code, please contact the corresponding author of the associated publication.
