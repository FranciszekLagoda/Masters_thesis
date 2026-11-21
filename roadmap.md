# Master's Thesis Project Overview
## Project Title (Draft)
Structural Transformation and Economic Development: A Panel Clustering Analysis of Global Economies.

## Introduction
The primary objective of this Master's thesis is to examine the relationship between structural economic composition and levels of macroeconomic development across multi-country panel dataset overtime and answering the question of whether it is possible for a country to develop without changing its economic structure.

Using unsupervised machine learning techniques - specifically cluster analysis - this study aims to construct an empirical taxonomy of economic structures based on sectoral outputs, labor distribution, trade composition, government involvement and other key macroeconomics indicators. By tracking how individual countries transition between identified countries transition between identified structural clusters across different time horizons, the analysis evaluates whether structural shifts significantly correlate with progression in overall economic development indicators (e.g., GDP per capita, productivity metrics, human development indices).

To handle the multi-country, multi-year panel data efficiently, the project employs a modern data engineering pipeline. Data is extracted via Python APIs directly from international databases (primarily the World Bank API). Data ingestion, cleaning, and feature engineering follow a Medallion Architecture (Bronze, Silver, and Gold layers).

## Project Roadmap & Section Breakdown
1. Literature Review and operationalization of variables
2. Data Engineering (Medallion Architecture)
3. Data exploration and Clustering
4. Dynamic analysis and development
5. Data validation and Robustness Checks
6. Redaction and latex

### Phase 1: Literature & Variable Selection
- [ ] **Literature Review:** Synthesize key theories of structural change (Lewis, Kuznets, Rodrik, Hausmann) and macroeconomic clustering studies into `01_literature/matrix.md`.
- [ ] **Variable Mapping:** Define operational indicators for economic structure (sectoral output, labor shares, trade, government role) and development outcomes (GDP per capita PPP, labor productivity, HDI).
- [ ] **Data Dictionary:** Create `data/data_dictionary.csv` with exact World Bank WDI (and supplementary API) indicator codes.

---

### Phase 2: Data Pipeline (Medallion Architecture)
- [ ] **Bronze Layer (`01_ingest_bronze.py`):** Extract raw multi-country, multi-year series via Python APIs into immutable `.parquet` files.
- [ ] **Silver Layer (`02_clean_silver.py`):** Harmonize ISO3 country codes, filter out regional aggregates, diagnose missing data, and impute short gaps.
- [ ] **Gold Layer (`03_build_gold.py`):** Engineer structural ratios, separate structural features ($X$) from development metrics ($Y$), and apply Z-score standardization.

---

### Phase 3: Clustering & Economic Taxonomy
- [ ] **EDA & PCA (`01_eda_pca.py`):** Analyze descriptive statistics, correlations, and principal components to inspect the structural feature space.
- [ ] **Clustering Models (`02_clustering.py`):** Train and compare K-Means, Hierarchical Clustering, and GMM; select optimal $k$ using Silhouette/Davies-Bouldin scores and economic interpretability.
- [ ] **Cluster Profiling:** Label and describe each structural regime (e.g., *Agrarian*, *Resource-Driven*, *Industrializing*, *Service-Based*).

---

### Phase 4: Dynamic Transitions & Hypothesis Testing
- [ ] **Transition Matrices (`03_transitions.py`):** Track country movements between clusters over time using Markov transition matrices and Sankey diagrams.
- [ ] **Trajectory Classification:** Group countries into *Structural Upgrading*, *Stagnation*, or *Deindustrialization* paths.
- [ ] **Development Impact Tests (`04_hypothesis_testing.py`):** Compare GDP pc, productivity, and HDI growth between transitioning and non-transitioning economies; examine resource-rich outliers.

---

### Phase 5: Robustness Checks & Thesis Writing
- [ ] **Sensitivity Analysis (`05_robustness.py`):** Test stability excluding oil/resource economies, changing time windows, and using alternative clustering/imputation methods.
- [ ] **Visuals & Tables:** Export clean LaTeX/Quarto tables and publication-ready figures into `thesis/`.
- [ ] **Drafting & Finalization:** Write Chapters 1–5, verify all BibTeX citations, and compile the final manuscript.