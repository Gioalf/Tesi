# RFI Performance & Punctuality Analysis

This repository contains the data processing pipelines used to analyze railway operations on RFI data, train punctuality, and suppressions. The codebase is divided into two distinct modules to handle different levels of data granularity.

## Repository Structure
* **PARTE1:** Processes macro-level data and generates the Executive Punctuality Report.
* **PARTE2:** Processes granular train movement data and generates weekly summary aggregations.

## Prerequisites
To run these notebooks, ensure you have a standard Python environment installed with the following libraries:
* `pandas`
* `numpy`

## How to Run the Pipeline

**For Part 1:**
1. Place the required `data.zip` file directly into the `PARTE1/INPUT/` directory.
2. Open and run `Parte1.ipynb`.
3. The notebook will extract the raw data, process it, and automatically save the `Executive_Punctuality_Report_4weeks.xlsx` to the `PARTE1/OUTPUTS/` directory.

**For Part 2:**
1. Place the required `data.zip` file directly into the `PARTE2/INPUT/` directory.
2. Open and run `Parte2.ipynb`.
3. The notebook will automatically save the granular train data and macro weekly summaries to the `PARTE2/OUTPUTS/` directory.

*Note: Raw data files and generated outputs are intentionally excluded from this repository via `.gitignore` to maintain a lightweight codebase.*