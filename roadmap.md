# Master's Thesis Project Overview
## Project Title (Draft)
Structural Transformation and Economic Development: A Panel Clustering Analysis of Global Economies.

## Introduction
The primary objective of this Master's thesis is to examine the relationship between structural economic composition and levels of macroeconomic development across multi-country panel dataset overtime and answering the question of whether it is possible for a country to develop without changing its economic structure.

Using unsupervised machine learning techniques - specifically cluster analysis - this study aims to construct an empirical taxonomy of economic structures based on sectoral outputs, labor distribution, trade composition, government involvement and other key macroeconomics indicators. By tracking how individual countries transition between identified countries transition between identified structural clusters across different time horizons, the analysis evaluates whether structural shifts significantly correlate with progression in overall economic development indicators (e.g., GDP per capita, productivity metrics, human development indices).

To handle the multi-country, multi-year panel data efficiently, the project employs a modern data engineering pipeline. Data is extracted via Python APIs directly from international databases (primarily the World Bank API). Data ingestion, cleaning, and feature engineering follow a Medallion Architecture (Bronze, Silver, and Gold layers).

---

## Project Roadmap & Section Breakdown
1. Literature Review and operationalization of variables
2. Data Engineering (Medallion Architecture)


### Phase 1: Literature & Variable Selection
1. Find starting literature.
    1. Find 3-5 classics for the topic. 
    2. Use ResearchRabbit or Litmaps to find related work. 
    3. Save them as pdf and add to bibtex.
2. Prepare text for AI (pdf -> md)
    1. Use Python to save md as tekst. Keep headings and page numbers.

---

### Phase 2: Data Pipeline (Medallion Architecture)
- [ ] **Bronze Layer (`01_ingest_bronze.py`):** Extract raw multi-country, multi-year series via Python APIs into immutable `.parquet` files.
- [ ] **Silver Layer (`02_clean_silver.py`):** Harmonize ISO3 country codes, filter out regional aggregates, diagnose missing data, and impute short gaps.
- [ ] **Gold Layer (`03_build_gold.py`):** Engineer structural ratios, separate structural features ($X$) from development metrics ($Y$), and apply Z-score standardization.
