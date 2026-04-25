# MSK-CHORD NSCLC Survival Analysis

## Overview
This repository contains the code, data processing pipelines, and modeling results for my final project. The project investigates the predictive value of rare gene mutations on long-term survival in Non-Small Cell Lung Cancer (NSCLC) patients using the MSK-CHORD dataset. 

I compare traditional linear models (Lasso-Cox) with non-linear machine learning approach (Random Survival Forests) across three feature engineering strategies to handle rare mutations.

## Project Website
**To view the project website, directly open the `website/docs/index.html` file in a web browser.**

## Repository Structure

### Data & Processing
* **`msk_chord_2024/`**: Directory containing the initial raw data from the MSK-CHORD cohort.
* **`Data_process.qmd`** & **`Data_process.pdf`**: The Quarto script (and compiled PDF report) used to clean and preprocess the raw clinical and genomic data.
* **`nsclc.csv`**: The finalized, clean dataset used for model building.

### Modeling
The modeling phase is split into three separate Quarto documents, each testing a different feature engineering approach to evaluate how well rare mutations can be utilized:

* **`NSCLC_Modeling_1.qmd`** & **`.pdf`**: **Feature Filtering**
    * *Baseline approach filtering for frequently mutated genes (e.g., >3% frequency).*
* **`NSCLC_Modeling_2.qmd`** & **`.pdf`**: **Rarity Weighting**
    * *Applies weights to rare mutations to retain up to 509 genes without compromising model stability.*
* **`NSCLC_Modeling_3.qmd`** & **`.pdf`**: **Biological Pathway Aggregation**
    * *Aggregates rare gene mutations into 112 biological pathways to capture broader genomic signals.*

### Project Files
* **`Final_629code.Rproj`**: The RStudio Project file. Open this file in RStudio to set the working directory automatically and run the `.qmd` scripts.

## How to Run the Code
1. Clone this repository to your local machine.
2. Open the `Final_629code.Rproj` file in RStudio.
3. Ensure you have the necessary R packages installed (e.g., `survival`, `glmnet`, `randomForestSRC`, `tidyverse`).
4. (Optional) Re-run `Data_process.qmd` to see how the raw data was cleaned into `nsclc.csv`.
5. Run the modeling scripts (`NSCLC_Modeling_1.qmd`, `2`, and `3`) to reproduce the analysis, ROC curves, and performance metrics.
