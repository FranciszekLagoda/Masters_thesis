## Project structure
thesis-project/
│
├── 01_literature/          #
│
├── 02_data/                # Data, medalion architecture
│   ├── bronze/             # Raw data from external sources
│   ├── silver/             # Cleared data
│   └── gold/               # Clustering ready data
│
├── 03_src/                 # Python code
│   ├── 01_etl/             # Scripts: download -> clean -> scale
│   ├── 02_models/          # Scripts: clustering, transition matrices, statistical tests
│   └── notebooks/          # Jupyter Scratchpad for Quick Tests and Graphs
│
├── 04_outputs/             # Analysis results (assigned clusters, charts, .tex/.csv tables)
│
├── 05_thesis/              # Master's thesis text
│
├── data_dictionary.csv     # Lista wskaźników i ich dokładnych kodów z World Bank API
├── config.py               
└── ROADMAP.md              # Plan pracy