# Business Statistics Assignment - Customer Segmentation Analysis

## Overview

This repository contains a comprehensive business statistics assignment focused on customer segmentation and behavioral analysis using advanced statistical and machine learning techniques. The project analyzes customer transaction data to identify distinct customer segments and derive actionable business insights.

## Dataset

The analysis is based on the **TaoYin User Transactions** dataset (`TaoYin_User_Transactions_v2.parquet`), which contains:
- **492,731 transaction records** from 2020-2022
- Customer transaction details including volume, pricing, and delivery information
- Product categorization data for behavioral analysis

### Key Features Analyzed:
- **Recency**: Time since last purchase
- **Total Purchases**: Number of transactions per customer
- **Average Profit**: Profitability per customer
- **Average Volume**: Purchase volume per transaction
- **Postcode Analysis**: Delivery vs. customer location patterns
- **Category Diversity**: Product category preferences

## Methodology

### 1. Exploratory Data Analysis (EDA)
- **Univariate Analysis**: Distribution analysis, outlier detection, descriptive statistics
- **Bivariate Analysis**: Correlation analysis using Spearman correlation
- **Data Quality Assessment**: Missing value analysis and data type validation

### 2. Feature Engineering
- Customer-level feature creation from transaction data
- RFM (Recency, Frequency, Monetary) analysis components
- Behavioral indicators (category diversity, delivery patterns)
- Outlier removal using quantile-based methods
- Feature scaling and weighting based on standard deviation

### 3. Clustering Algorithms

#### K-Means Clustering
- **Elbow Method**: Optimal cluster number determination
- **Metrics**: Silhouette Score, Davies-Bouldin Index, Calinski-Harabasz Index
- **Results**: 3-cluster solution for general customer segmentation

#### DBSCAN Clustering
- **Parameter Tuning**: KNN-based epsilon determination
- **Density-based**: Identifies clusters of varying shapes and sizes
- **Noise Detection**: Handles outliers as separate category

#### HDBSCAN Clustering
- **Hierarchical Density**: Advanced density-based clustering
- **Best Performance**: Highest scores across all evaluation metrics
- **Selected Model**: Chosen for final analysis due to superior performance

### 4. Principal Component Analysis (PCA)
- **Dimensionality Reduction**: 2-component solution
- **Variance Explanation**: ~99.5% cumulative explained variance
- **Cluster Visualization**: 2D and 3D projections of customer segments
- **Feature Interpretation**: Component loadings and cluster characteristics

### 5. Statistical Testing
- **Normality Tests**: Shapiro-Wilk test for distribution assessment
- **Variance Tests**: Levene's test for equal variances
- **Post-hoc Analysis**: 
  - Tukey's HSD for parametric comparisons
  - Games-Howell for non-parametric comparisons
- **Category Diversity Analysis**: Statistical comparison across customer groups

## Key Findings

### Customer Segmentation Results

#### General Customer Analysis (HDBSCAN - 3 Clusters):
1. **Promotional Customers (Cluster 0)**: Low-profit customers with small purchase volumes
2. **Average Customers (Cluster 1)**: Majority segment with moderate negative profit
3. **High-Volume Customers (Cluster -1)**: Outliers with large volumes but low profitability

#### Dropshipper Analysis (K-Means - 3 Clusters):
1. **Promotional Dropshippers**: Small profit, promotion-focused
2. **Average Dropshippers**: Moderate volume, negative profit impact
3. **High-Volume Dropshippers**: Significant volume but company losses

### Business Insights

#### Profitability Analysis:
- **Negative Average Profit**: Company operates at loss for customer acquisition
- **Outlier Dependency**: Heavy reliance on few high-value customers
- **Dropshipper Impact**: Identified but not significantly more problematic than regular customers

#### Statistical Testing Results:
- **Category Diversity**: No significant differences in customer behavior across product categories
- **P-values > 0.05**: Cannot reject null hypothesis of equal means across groups

## Technical Implementation

### Dependencies
```python
# Core Libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Machine Learning
from sklearn.cluster import KMeans, DBSCAN
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import silhouette_score, davies_bouldin_score, calinski_harabasz_score

# Advanced Clustering
import hdbscan

# Statistical Testing
from scipy.stats import shapiro, levene
from statsmodels.stats.multicomp import pairwise_tukeyhsd
import pingouin as pg
```

### Key Functions Implemented:
- **Visualization**: Box plots, density plots, 2D/3D scatter plots, heatmaps
- **Clustering**: Elbow method, epsilon determination, metric calculation
- **Statistical Testing**: Automated test selection based on normality and variance assumptions
- **Data Processing**: Outlier removal, scaling, feature weighting

## File Structure

```
bs-statistic/
├── README.md                           # This file
├── assignment_solution.ipynb          # Complete analysis notebook
├── assignment_report.docx             # Written report
├── assignment_task.pdf                # Assignment requirements
└── datasets/
    └── TaoYin_User_Transactions_v2.parquet  # Transaction data
```

## Usage

1. **Install Dependencies**:
   ```bash
   pip install hdbscan pingouin
   ```

2. **Run Analysis**:
   - Open `assignment_solution.ipynb` in Jupyter Notebook
   - Execute cells sequentially for complete analysis
   - Results include visualizations, statistical tests, and business insights

## Evaluation Metrics

### Clustering Performance:
- **Silhouette Score**: 0.62 (HDBSCAN) - Excellent cluster separation
- **Davies-Bouldin Index**: 0.32 (HDBSCAN) - Low intra-cluster distance
- **Calinski-Harabasz Index**: 364.76 (HDBSCAN) - High inter-cluster separation

### Statistical Significance:
- All hypothesis tests conducted with α = 0.05
- Proper test selection based on data assumptions
- Comprehensive post-hoc analysis for multiple comparisons

## Business Applications

This analysis provides actionable insights for:
- **Customer Segmentation**: Targeted marketing strategies
- **Profitability Optimization**: Focus on high-value customer acquisition
- **Risk Management**: Dropshipper identification and mitigation
- **Product Strategy**: Category-based customer behavior understanding