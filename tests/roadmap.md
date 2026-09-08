# Master's Thesis Project Overview
## Project Title (Draft)
Structural Transformation and Economic Development: A Panel Clustering Analysis of Global Economies.

## Introduction
The primary objective of this Master's thesis is to examine the relationship between structural economic composition and levels of macroeconomic development across multi-country panel dataset overtime.

Using unsupervised machine learning techniques - specifically cluster analysis - this study aims to construct an empirical taxonomy of economic structures based on sectoral outputs, labor distribution, trade composition, government involvement and other key macroeconomics indicators. By tracking how individual countries transition between identified countries transition between identified structural clusters across different time horizons, the analysis evaluates whether structural shifts significantly correlate with progression in overall economic development indicators (e.g., GDP per capita, productivity metrics, human development indices).

To handle the multi-country, multi-year panel data efficiently, the project employs a modern data engineering pipeline. Data is extracted via Python APIs directly from international databases (primarily the World Bank API). Data ingestion, cleaning, and feature engineering follow a Medallion Architecture (Bronze, Silver, and Gold layers). While initial exploration and prototype clustering are conducted in local Python environments, the pipeline and analytics layer are structured for deployment within Microsoft Fabric to demonstrate enterprise-grade data engineering and analytical workflows.

## Project Roadmap & Section Breakdown
1. Problem Definition and Project Scope
1. Medallion Data Engineering
1. Exploratory Data Analysis & Clustering
1. Dynamic Analysis & Econometrics
1. Fabric Integration

## Master's Thesis Project Roadmap

### Phase 1: Problem Definition & Data Sourcing Scope
* **Objective:** Define country coverage, timeframes, core indicators, and setup repository architecture.
* **Key Tasks:**
  * Define panel scope (e.g., 100+ countries, timeframe 1990–2025).
  * Select economic structure variables (sectoral GDP shares for agriculture, industry, services; employment distribution; export complexity/high-tech export share; capital formation).
  * Select development outcome variables (real GDP per capita, HDI, total factor productivity growth).
  * Establish project repository, folder hierarchy (Medallion schema), and version control (`.gitignore`, `.venv`).

### Phase 2: Medallion Data Engineering Pipeline
* **Objective:** Programmatically ingest, clean, and refine World Bank API panel data into analytical data layers.
* **Key Tasks:**
  * **Bronze Layer (Raw):** Write Python scripts using `wbgapi` or `requests` to fetch multi-country, multi-year raw data and store in raw formats (`.json` / raw `.parquet`).
  * **Silver Layer (Cleaned & Standardized):** Harmonize country identifiers (ISO3 codes), handle missing panel observations (imputation / interpolation strategies), flatten multi-index frames, and standardize data types.
  * **Gold Layer (Feature Engineered):** Construct structural concentration indices, compute multi-year rolling averages to reduce noise, calculate structural shift metrics, and build final modeling-ready tables.

### Phase 3: Unsupervised Cluster Analysis
* **Objective:** Identify empirical structural economic archetypes across time and geography using unsupervised machine learning.
* **Key Tasks:**
  * Preprocess feature space (feature scaling using `StandardScaler`/`RobustScaler`, dimensionality reduction via PCA/UMAP if necessary).
  * Implement and compare clustering algorithms ($k$-Means, Hierarchical Clustering, Gaussian Mixture Models).
  * Evaluate optimal cluster count ($k$) using Silhouette Scores, Elbow Method, and Calinski-Harabasz Index.
  * Define, label, and interpret identified structural clusters (e.g., *Agrarian-Dominant*, *Resource-Exporting*, *Manufacturing-Led*, *High-Tech Service Economies*).

### Phase 4: Dynamic Transition & Development Correlation Analysis
* **Objective:** Quantify country transitions between structural clusters over time and analyze their statistical relationship with economic development.
* **Key Tasks:**
  * Construct Markov transition matrices to quantify transition probabilities between structural clusters across 5/10-year intervals.
  * Analyze economic performance trajectories (e.g., GDP per capita growth acceleration) pre- and post-transition.
  * Estimate panel data econometric models (fixed-effects / random-effects / event-study models) testing whether cluster shifts correlate significantly with economic growth and development outcomes.

### Phase 5: Microsoft Fabric Deployment & Final Thesis Integration
* **Objective:** Migrate local data pipeline into Microsoft Fabric (Lakehouse architecture) and document research findings.
* **Key Tasks:**
  * Provision a Microsoft Fabric Lakehouse environment and configure OneLake storage for Bronze/Silver/Gold Delta tables.
  * Port local Pandas transformation scripts into Fabric PySpark Notebooks.
  * Build interactive Power BI reporting dashboards over the Gold layer to visualize cluster transitions and regional geographic maps.
  * Finalize academic write-up detailing methodology, data architecture, empirical findings, and policy implications.