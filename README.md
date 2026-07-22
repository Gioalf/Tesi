# RFI Performance & Punctuality Analysis

This repository contains the data processing pipelines used to analyze railway operations on RFI data, train punctuality, and suppressions. The codebase is divided into two distinct modules to handle different levels of data granularity.

## Repository Structure
* **PARTE1:** Processes macro-level data and generates the Executive Punctuality Report.
* **PARTE2:** Processes granular train movement data and generates weekly summary aggregations.

## The Automated Pipeline
Both modules run a fully automated 4-phase processing engine:
1. **Data Import & Categorization:** Automatically unzips the raw data, flattens nested directories, and categorizes files based on internal metadata (e.g., Punctuality vs. Suppressions, Forward vs. Reverse directions).
2. **Aggregation & Cleaning:** Runs strict sanity and chronological checks to purge anomalies, aggregates daily data into ISO weeks, and drops non-indicative routes or low-traffic periods. 
3. **Master Merge & Matrix Generation:** Stitches the cleaned data together into master datasets, calculating final network KPIs and generating geographically sorted stop-sequence matrices.
4. **Trend Calculation & Report Generation:** Computes rolling averages, dynamic status flags (deltas/thresholds), and historical percentiles, outputting formatted Excel reports or CSV summaries.

## Prerequisites
To run these notebooks, ensure you have a standard Python 3 environment installed with the following libraries:
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `openpyxl`

## How to Run the Pipeline

**For Part 1:**
1. Place the required `data.zip` file directly into the `PARTE1/INPUT/` directory.
2. Open and run `Parte1.ipynb`.
3. The notebook will extract the raw data, process it, and automatically save the `Executive_Punctuality_Report_4weeks.xlsx` to the `PARTE1/OUTPUTS/` directory.

**For Part 2:**
1. Place the required `data.zip` file directly into the `PARTE2/INPUT/` directory.
2. Open and run `Parte2.ipynb`.
3. The notebook will process the granular train data, apply node anonymization, and automatically save two files to the `PARTE2/OUTPUTS/` directory:
   * `1_Granular_Train_Data.csv`
   * `2_Macro_Weekly_Summary.csv`

*Note: Raw data files and generated outputs are intentionally excluded from this repository via `.gitignore` to maintain a lightweight codebase.*

##DATA INPUT:
* **Part 1:** I dati richiesti per la parte 1 sono ottenuti tramite interrogazione su PIC ``
* **Part 2:** I dati richiesti per la parte 2 sono ottenuti tramite interrogazione su PIC `Puntualità e Ritardi Località - Anno corrente e precedente` e `Tipo Ritardo = 'Partenza dalla Località'`
