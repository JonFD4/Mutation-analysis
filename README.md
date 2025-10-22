# Mutation-analysis

## Project Overview
 This project analyses somatic data derived from cancer sequencing dataset. The goal is to identify frequently mutated genes, annotate the functional impact of variants, and visualise mutation pythons using python
 The purpose of this project is to:
 * Explore and undertsand real_worl genomic mutation data
 * Implement professional data analysis workflows
 * Build a reprodcible web-based data visualisation app
 
    The project uses mutation data (in TCGA-style Mutation Annotation Format) to explore:
    * Which genes are most frequently mutated
    * What kinds of mutation types occur
    * How data can be cleaned, visualized, and shared

### Project Structure
genomic-mutation-project/
│
├── data/
│   ├── raw/                 # Original data_mutations.txt
│   ├── processed/           # Cleaned CSV/JSON for web and analysis
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_data_analysis.ipynb
│   └── 04_web_app_prototype.ipynb
│
├── docs/
│   ├── data_dictionary.md   # Explains each column
│   └── web_architecture.md  # Design for the web app & cloud setup
│
├── results/
│   ├── top10_mutated_genes.png
│   └── summary_tables/
│
├── api/                     # (Future) API layer for web app
│   └── app.py or index.ts
│
├── frontend/                # (Future) TypeScript or Next.js web frontend
│
└── README.md

## Set up and requirements

In requirements.txt
``` txt
pandas
numpy
matplotlib
seaborn
jupyterlab
```
```bash
# 1. Clone the repository
git clone https://github.com/yourusername/genomic-mutation-project.git
cd genomic-mutation-project

# 2. Create virtual environment
python -m venv .venv
source venv/bin/activate  # (or venv\Scripts\activate on Windows)

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch Jupyter Notebook
jupyter lab
```

## File list
* [Mutation dataset](data/raw/data_mutations.txt)
* [Data-exploration.ipynb](notebooks/data_exploration.ipynb)
* [Dictionary](docs/data_dictionary.md)

