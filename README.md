# AI-Assisted-Audit-Platform

# AI-Assisted Audit Execution Platform

> **⚠️ ACADEMIC EMBARGO NOTICE:** > The raw Python source code and proprietary datasets for this repository are currently under a strict academic embargo pending final approval and publication by my faculty advisor. The system architecture, design choices, and logic flow are documented below and can be discussed in detail during live interviews.

## 📌 Project Overview
Small business audits suffer from a massive resource bottleneck. Junior auditors routinely spend 25 to 60 hours on low-judgment, repetitive substantive procedures like tie-outs, recalculations, and anomaly flagging. 

This project solves that bottleneck by deploying an end-to-end **unsupervised machine learning pipeline** that automates general ledger data verification and autodrafts review-ready audit documentation. 

**The Result:** Manual workflows that previously took 40+ hours were compressed into approximately 15 minutes, achieving up to a 99.7% efficiency gain.

## 🏗️ System Architecture & Constraints
The hardest part of implementing AI in financial auditing is navigating the strict design constraints of audit documentation defensibility (ISA 230 and AS 1215). A black-box LLM hallucination is a critical failure; every output requires 100% traceability.

To solve this, the architecture intentionally separates mathematical analytics from language generation across three distinct modules:

### Module 1: Unsupervised Machine Learning (Anomaly Detection)
* **Models Used:** Isolation Forest, Median Absolute Deviation (MAD), and Robust Z-scores.
* **Function:** Learns normal general ledger (GL) patterns and mathematically isolates multivariate accounting anomalies.
* **Design Choice:** Operates without any labeled training data or external API calls to preserve data privacy.

### Module 2: Statistical Modeling (Business Logic)
* **Models Used:** OLS (Ordinary Least Squares) and Ridge Regression.
* **Function:** Learns the relationship between operational drivers and monthly account balances.
* **Design Choice:** Fully interpretable—every coefficient directly maps to a real business relationship (e.g., dollars per payroll hour) rather than relying on opaque deep learning weights.

### Module 3: Deterministic Text Generation (Audit Defensibility)
* **Framework:** Python-based rule engine.
* **Function:** Reads structured flag outputs from Modules 1 and 2 and dynamically fills pre-written narrative templates to draft the final workpapers.
* **Design Choice:** **No Generative AI or LLMs were used for text generation.** This was a deliberate architectural choice to guarantee that every flagged anomaly is perfectly explainable and traceable back to the raw source data, satisfying strict compliance standards.

## 🏆 Awards & Recognition
* **AI-Enabled Research Award:** Won 1st Place for AI-enabled research at the CSU Student Research Competition (hosted by San Jose State University, April 2025).
* **International Academic Acceptance:** Co-authored the associated paper, *"Wait! Let's Use AI First: A Conceptual AI Model to Assist Junior Auditors with Standard Procedures,"* which has been accepted for presentation at the **35th Asian-Pacific Conference on International Accounting Issues** (Nov 2026).

## 💻 Tech Stack
* **Languages:** Python, SQL
* **Libraries:** Pandas, Statsmodels, Scikit-learn (Isolation Forest)
* **Methodologies:** Unsupervised Learning, Robust Statistics, Rule-Based Natural Language Generation
* 
### Recommended Repository Structure

Create this folder structure on your local machine and organize the code you provided into the respective files:

```text
AI_Audit_Research/
│
├── src/                                          
│   ├── module1_anomaly_detection.py              # Code from Source 1
│   ├── build_module2_notebook.py                 # Code from Source 2
│   ├── expectation_variance_module.py            # Code from Source 3
│   └── module3_exception_documentation.py        # Code from Source 5
│
├── notebooks/             
│   └── module2_expectation_variance_modeling.ipynb # Code from Source 4
│
├── requirements.txt       
├── .gitignore             
└── README.md              

```

---

### `requirements.txt`

Your code imports several standard libraries (like `json`, `argparse`, `pathlib`, `re`, and `collections`), which do not need to be installed. Save the following third-party dependencies into a `requirements.txt` file:

```text
numpy
pandas
scikit-learn
matplotlib
nbformat
ipython

```

---

### `README.md` Template

Copy and paste this markdown into your `README.md` file. It accurately summarizes the three modules based on your code:

```markdown
# AI Audit Research 🔍

## Overview
This repository contains an AI-assisted audit analytics prototype designed for a small business environment. The goal is to evaluate general ledger lines and account balances using unsupervised machine learning and statistical modeling to generate preliminary analytic indicators for auditor review.

## Project Architecture

This project is broken down into three core modules:

### Module 1: Anomaly Detection
* Performs audit-support anomaly detection for general ledger lines[cite: 1].
* Utilizes `scikit-learn`'s Isolation Forest algorithm to score the supplied general ledger population[cite: 1].
* Injects synthetic anomalies to validate and evaluate detection performance[cite: 1].

### Module 2: Expectation and Variance Modeling
* Estimates expected monthly account values and ranks unusual variances that may warrant auditor follow-up[cite: 2].
* Fits interpretable OLS (Ordinary Least Squares) and Ridge regression models with time-aware features[cite: 2, 3].
* Performs a time-based train/test split to validate expectations on later periods[cite: 2].

### Module 3: Exception Documentation Output
* Converts flagged results from Module 1 and Module 2 into deterministic, audit-support documentation drafts[cite: 5].
* Generates markdown reports and workpaper paragraphs detailing why items were flagged, the likely business context, and suggested auditor follow-up requests[cite: 5].

## Installation
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/AI_Audit_Research.git](https://github.com/your-username/AI_Audit_Research.git)

```

2. Navigate to the directory:
```bash
cd AI_Audit_Research

```


3. Install the required dependencies:
```bash
pip install -r requirements.txt

```



## Usage

**Module 1:**
To score a general ledger CSV and flag anomalies, run:

```bash
python src/module1_anomaly_detection.py score --input-csv <path_to_csv>

```

**Module 2:**
To generate the Expectation and Variance notebook:

```bash
python src/build_module2_notebook.py

```

**Module 3:**
To generate the final exception markdown reports based on the outputs of Modules 1 and 2:

```bash
python src/module3_exception_documentation.py

```

## Disclaimer

These outputs are preliminary analytic indicators. Unusual variances or anomalies may warrant follow-up, but they do not imply audit conclusions on their own.

```

---

### How to Upload to GitHub

Once you have saved the code into the `AI_Audit_Research` directory structure above, open your terminal, navigate to the `AI_Audit_Research` folder, and run the following commands:

1. **Initialize Git:**
   ```bash
   git init

```

2. **Stage your files:**
```bash
git add .

```


3. **Commit your files:**
```bash
git commit -m "Initial commit: Added Modules 1, 2, and 3 for AI Audit Research"

```


4. **Link to GitHub:** Go to GitHub.com, create a new repository named `AI_Audit_Research`, and copy the provided repository URL. Then run:
```bash
git remote add origin <your-new-github-repo-url>

```


5. **Push your code:**
```bash
git branch -M main
git push -u origin main

```
