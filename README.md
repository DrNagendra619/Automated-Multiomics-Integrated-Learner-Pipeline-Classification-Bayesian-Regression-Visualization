# Automated-Multiomics-Integrated-Learner-Pipeline-Classification-Bayesian-Regression-Visualization
Automated Multiomics IntegratedLearner Pipeline Stacked Classification Bayesian Regression and Interactive Visualization
# Automated Multi-omics Prediction Pipeline (IntegratedLearner)

This repository contains the R script implementing a robust, end-to-end multi-omics prediction framework based on the **IntegratedLearner** R package. The pipeline demonstrates **Stacked Generalization (SuperLearner)** for superior prediction accuracy and exports fully **interactive visualizations** using Plotly and DT.

---

## ✨ Key Features

* **Stacked Ensemble Modeling:** Combines predictions from individual omics layers (e.g., Microbiome, Metabolites) using a meta-learner (NNLS) to improve accuracy.
* **Prediction Examples:** Executes two distinct workflows:
    1.  **Binary Classification:** Prediction of IBD Disease Status (using PRISM dataset).
    2.  **Continuous Regression:** Prediction of Gestational Age (using Pregnancy dataset).
* **Dual Output Reporting:** Generates results in both **Static PNG** files (for reports) and **Interactive HTML** files (for dynamic exploration).
* **Environment Hardening:** Includes explicit checks and setup for the Java Virtual Machine (JVM), which is required for high-performance computing in the pipeline.

---

## 🛠️ Prerequisites & Setup

This pipeline requires **R (version 4.0 or higher)** and a correctly configured **64-bit Java Development Kit (JDK)**.

### 1. Configure Java Memory (Crucial Step)

Due to the size and nature of multi-omics data, the script requires a high memory allocation for the JVM engine (`bartMachine` and `SuperLearner`).

⚠️ **Before running the script**, execute this command in your R console to allocate 5GB of RAM to Java:

```r
options(java.parameters = "-Xmx5g")
2. Install Required Packages

Install the necessary packages, including the IntegratedLearner package from the author's GitHub repository:
# 1. Install standard packages
install.packages(c("devtools", "tidyverse", "SuperLearner", "bartMachine", "plotly", "DT", "pROC", "htmlwidgets", "caret", "cowplot", "bayesplot"))

# 2. Install IntegratedLearner from GitHub
devtools::install_github("himelmallick/IntegratedLearner", upgrade = "never")
🚀 Usage

Once prerequisites are met, run the script using the source() command. All necessary data will be downloaded automatically from the referenced public URLs.
# 1. Ensure you have run the options(java.parameters) command!

# 2. Set the script to run, ensuring the Java path is correct for your system.
# Note: The script uses the hardcoded path from the successful setup.
source("Automated Multiomics IntegratedLearner Pipeline Stacked Classification Bayesian Regression and Interactive Visualization.R")
📦 Output & Reporting

The script automatically organizes all results into the specified local directory: D:\DOWNLOADS.
File Type,Description,Purpose
.html,Interactive Plotly/DT Widgets,"Explore dynamic ROC curves, prediction scatter plots, and searchable layer weights."
.png,Static Images,High-resolution versions of all primary visualizations (suitable for presentations/reports).
.csv,Data Tables,Raw prediction scores and final layer weights for custom analysis.
Data Sources & References
Dataset,URL Access (Used in Script),Original Publication
IBD / PRISM,https://github.com/himelmallick/IntegratedLearner/blob/master/data/PRISM.RData?raw=true,Franzosa et al. (2019)
Pregnancy,https://github.com/himelmallick/IntegratedLearner/blob/master/data/pregnancy.RData?raw=true,Ghaemi et al. (2019)
