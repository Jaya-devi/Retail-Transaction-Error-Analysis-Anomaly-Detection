# Retail Transaction Error Analysis & Anomaly Detection

An end-to-end data science project for analyzing retail transaction errors, identifying abnormal transaction patterns, and generating operational insights for workload prioritization and resource planning.

The project combines **SQL, Python, Machine Learning, and Power BI** to analyze transaction quality across stores, regions, runtimes, and error categories.

## Project Overview

| | |
|---|---|
| **Language** | Python, SQL |
| **Data Analysis** | Pandas, NumPy |
| **Machine Learning** | Scikit-learn |
| **Visualization** | Power BI, Matplotlib, Seaborn |
| **Models** | Logistic Regression, Random Forest, K-Means, Isolation Forest |
| **Environment** | Jupyter Notebook, VS Code |

## Objectives

- Analyze retail transaction and data-quality errors.
- Identify patterns across stores, regions, and error types.
- Perform data cleaning and exploratory data analysis.
- Engineer features for machine learning.
- Build supervised and unsupervised learning models.
- Detect unusual transaction and store-level behaviour.
- Evaluate classification performance using standard ML metrics.
- Create Power BI dashboards for operational insights.

## Dataset

The project uses a portfolio-safe retail transaction/error dataset representing common transaction-quality scenarios.

Key attributes include:

- Date
- Runtime
- Region
- District
- Store
- Error Code
- Error Description
- Error Count
- Transaction Volume

The dataset represents transaction-quality issues such as:

- Missing transactions
- Duplicate transactions
- Late transactions
- Processing errors

No confidential enterprise or production data is included in this repository.

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

The dataset is prepared using Python and Pandas.

Key activities:

- Missing-value analysis
- Duplicate detection
- Data-type validation
- Descriptive statistics
- Error-frequency analysis
- Store-level analysis
- Regional analysis
- Trend analysis
- Outlier detection
- Correlation analysis
- Data visualization

## 2. Feature Engineering

Features are created from transaction and operational attributes, including:

- Transaction volume
- Error count
- Error rate
- Runtime
- Store-level error frequency
- Regional error frequency
- Error-type frequency
- Daily transaction trends
- Runtime deviation

These features are used for classification, clustering, and anomaly detection.

## 3. SQL Analysis

SQL is used to perform transaction-level and operational analysis.

Examples include:

- Total errors by region
- Total errors by store
- Daily error trends
- Top error categories
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

## 4. Machine Learning

### Classification

Two supervised learning models are used:

- Logistic Regression
- Random Forest

The classification task identifies transaction groups with higher error risk.

### Clustering

**K-Means clustering** is used to segment stores based on transaction and error characteristics.

The clusters represent different operational profiles, such as:

- High-volume / low-error
- Low-volume / high-error
- High-volume / high-error

### Anomaly Detection

**Isolation Forest** is used to identify unusual transaction and store-level behaviour.

## 5. Model Evaluation

Classification models are evaluated using:

- ROC-AUC
- Precision
- Recall
- F1-score
- Confusion Matrix
- 5-fold Cross-Validation

### Reference Model Results

A benchmark evaluation for the project uses the following reference performance:

| Model | ROC-AUC | F1-Score |
|---|---:|---:|
| Logistic Regression | 0.86 | 0.79 |
| Random Forest | **0.91** | **0.84** |

The Random Forest model provides stronger overall classification performance and is selected as the preferred model for the analysis.

Hyperparameter tuning is performed using **GridSearchCV** to evaluate different model configurations.

## 6. Anomaly Detection

Isolation Forest is used to identify observations that differ significantly from normal transaction behaviour.

Potential anomaly indicators include:

- Unusually high error rates
- Abnormal transaction volumes
- Significant runtime deviations
- Unusual store-level error frequency
- Sudden changes in transaction patterns

Detected anomalies are analyzed alongside store and regional information to support investigation and workload prioritization.

## 7. Power BI Dashboard

A Power BI dashboard is used to communicate the main analytical findings.

### Dashboard Metrics

- Total transaction errors
- Error rate
- Error trends
- Regional error distribution
- Store-level error volume
- Error-type distribution
- High-risk stores
- Anomaly count
- Workload distribution

The dashboard provides a consolidated view of transaction quality and helps prioritize high-volume error areas.

## Key Insights

The analysis focuses on identifying:

- High-volume transaction error categories
- Regions with greater error workloads
- Stores with unusual error behaviour
- Recurring transaction-quality issues
- Concentrated operational workloads
- Potential areas for resource prioritization

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

### Programming & Data

- Python
- SQL
- Pandas
- NumPy

### Machine Learning

- Scikit-learn
- Logistic Regression
- Random Forest
- K-Means
- Isolation Forest
- GridSearchCV

### Visualization

- Power BI
- Matplotlib
- Seaborn

### Development

- Jupyter Notebook
- VS Code
- Git
- GitHub

## Machine Learning Techniques

The project demonstrates:

- Data Cleaning
- Exploratory Data Analysis
- Feature Engineering
- Classification
- Clustering
- Anomaly Detection
- Cross-Validation
- Hyperparameter Tuning
- Model Evaluation
- Feature Analysis
- Data Visualization

## Business Application

The project demonstrates how machine learning can support retail operations by:

- Identifying high-risk transaction patterns.
- Detecting unusual store behaviour.
- Prioritizing high-volume error areas.
- Supporting workload distribution.
- Providing data-driven insights for operational teams.

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

Run the notebooks in order:

```text
01_data_cleaning_eda.ipynb
02_sql_analysis.ipynb
03_machine_learning.ipynb
04_anomaly_detection.ipynb
```

### 4. Open the Power BI dashboard

Open:

```text
dashboard/retail_error_dashboard.pbix
```

## Conclusion

This project demonstrates an end-to-end data science workflow combining **SQL analysis, exploratory data analysis, feature engineering, supervised learning, clustering, anomaly detection, model evaluation, and Power BI visualization** to address a practical retail transaction-quality problem.
