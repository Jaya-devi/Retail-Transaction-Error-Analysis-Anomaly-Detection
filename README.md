# Retail Transaction Error Analysis & Anomaly Detection

This project analyzes retail transaction and data-quality errors to identify error patterns, high-risk stores, unusual transaction behaviour, and workload trends.

The project combines **SQL, Python, Machine Learning, and Power BI** to demonstrate an end-to-end data analysis and machine learning workflow for retail operations.

## Project Overview

| | |
|---|---|
| **Language** | Python, SQL |
| **Libraries** | Pandas, NumPy, Scikit-learn |
| **Machine Learning** | Classification, Clustering, Anomaly Detection |
| **Visualization** | Power BI, Matplotlib, Seaborn |
| **Environment** | Jupyter Notebook, VS Code |

## Objectives

- Analyze transaction errors across stores, regions, and error types.
- Identify recurring error patterns and high-risk transaction groups.
- Perform data cleaning, EDA, and feature engineering.
- Build supervised and unsupervised machine learning models.
- Detect unusual transaction and store-level behaviour.
- Evaluate model performance using standard ML metrics.
- Create dashboards to communicate findings and support workload prioritization.

## Dataset

The project uses a retail transaction/error dataset containing fields such as:

- Date
- Runtime
- Region / District
- Store
- Error Code
- Error Description
- Error Count
- Transaction Volume

The data represents common retail transaction-quality scenarios such as missing transactions, duplicate transactions, late transactions, and processing issues.

> **Note:** Sensitive or confidential enterprise data is not included in this repository. The project uses a portfolio-safe dataset representing the same analytical problem.

## Project Workflow

```text
Transaction Data
       ↓
Data Cleaning
       ↓
SQL Analysis
       ↓
EDA & Visualization
       ↓
Feature Engineering
       ↓
Machine Learning
       ↓
Model Evaluation
       ↓
Anomaly Detection
       ↓
Power BI Dashboard
```

## 1. Data Preparation & EDA

The dataset is cleaned and prepared using Python and Pandas.

Activities include:

- Missing-value analysis
- Duplicate detection
- Data-type validation
- Error-frequency analysis
- Store and regional analysis
- Trend analysis
- Outlier detection
- Correlation analysis
- Data visualization

### Feature Engineering

Features include:

- Error rate
- Transaction volume
- Error count
- Runtime
- Store-level error frequency
- Regional error frequency
- Error-type frequency
- Daily transaction trends

## 2. SQL Analysis

SQL is used to perform operational and transaction-level analysis.

Examples include:

- Error counts by region
- Error counts by store
- Error trends by date
- Top error types
- Store-level error rates
- Regional workload comparison

Example:

```sql
SELECT
    region,
    SUM(error_count) AS total_errors
FROM transactions
GROUP BY region
ORDER BY total_errors DESC;
```

## 3. Machine Learning

### Classification

The project uses:

- Logistic Regression
- Random Forest

The classification model identifies high-risk transaction patterns based on engineered transaction and error features.

### Clustering

**K-Means clustering** is used to group stores based on transaction and error characteristics.

Example groups may represent:

- High-volume / low-error stores
- Low-volume / high-error stores
- High-volume / high-error stores

### Anomaly Detection

**Isolation Forest** is used to identify unusual transaction and store-level behaviour.

## 4. Model Evaluation

Models are evaluated using:

- Cross-validation
- ROC-AUC
- Precision
- Recall
- F1-score
- Confusion Matrix

### Model Results

**Best Classification Model:** [TO UPDATE]

**ROC-AUC:** [TO UPDATE]

**F1-score:** [TO UPDATE]

The final model will be selected based on cross-validation and held-out test performance.

## 5. Anomaly Analysis

The anomaly detection stage identifies unusual transaction patterns based on features such as:

- Transaction volume
- Error rate
- Runtime
- Error frequency
- Store-level behaviour

Detected anomalies are analyzed to understand potential data-quality or processing issues.

## 6. Power BI Dashboard

A Power BI dashboard is created to communicate the main findings.

Dashboard views include:

- Total transaction errors
- Error trends
- Regional comparison
- Store-level error analysis
- Error-type distribution
- High-risk stores
- Workload distribution

The dashboard is designed to support **workload prioritization and resource planning**.

## Key Findings

The analysis focuses on identifying:

- High-volume error categories
- Regions with higher error workloads
- Stores with unusual error patterns
- Recurring transaction-quality issues
- Potential workload concentration

Final quantitative findings will be added after model and dashboard analysis.

## Project Structure

```text
Retail-Transaction-Anomaly-Detection/
│
├── data/
│
├── notebooks/
│   ├── 01_data_cleaning_eda.ipynb
│   ├── 02_sql_analysis.ipynb
│   ├── 03_machine_learning.ipynb
│   └── 04_anomaly_detection.ipynb
│
├── dashboard/
│   └── retail_error_dashboard.pbix
│
├── models/
│
├── outputs/
│
├── requirements.txt
└── README.md
```

## Technologies

**Programming:** Python, SQL

**Data Analysis:** Pandas, NumPy

**Machine Learning:** Scikit-learn

**Models:** Logistic Regression, Random Forest, K-Means, Isolation Forest

**Visualization:** Power BI, Matplotlib, Seaborn

**Development:** Jupyter Notebook, VS Code, Git/GitHub

## Key Skills Demonstrated

- Data Cleaning
- Exploratory Data Analysis
- SQL Analysis
- Feature Engineering
- Classification
- Clustering
- Anomaly Detection
- Cross-Validation
- Hyperparameter Tuning
- Model Evaluation
- Data Visualization
- Business Insight Generation

## How to Run

### 1. Clone the repository

```bash
git clone <repository-url>
cd Retail-Transaction-Anomaly-Detection
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebooks

Run the notebooks in the following order:

```text
01_data_cleaning_eda.ipynb
        ↓
02_sql_analysis.ipynb
        ↓
03_machine_learning.ipynb
        ↓
04_anomaly_detection.ipynb
```

### 4. Open the Power BI dashboard

Open the `.pbix` file from the `dashboard` folder.
