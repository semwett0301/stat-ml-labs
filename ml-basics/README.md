# Machine Learning Basics - Movie Revenue Prediction

## Overview

This repository contains a comprehensive machine learning project focused on predicting movie revenue using pre-production features. The project implements a complete ML pipeline from data preprocessing to model interpretation, utilizing advanced statistical techniques and multiple machine learning algorithms.

## Project Goal

**Predict movie opening weekend revenue** using pre-production features such as budget, genre, director, cast, and other film characteristics available before a movie's release.

## Dataset

The project analyzes movie data with pre-production features including:
- **Budget information**: Production budget, marketing budget
- **Creative team**: Director, cast members, writers
- **Film characteristics**: Genre, rating, runtime, language
- **Target variable**: Opening weekend revenue (`opening_weekend`)

## Methodology

### 1. Exploratory Data Analysis (EDA)
- **Data Quality Assessment**: Missing value analysis, data type validation
- **Distribution Analysis**: Statistical distribution examination for numerical features
- **Feature Engineering**: Creation of derived features and categorical encoding
- **Outlier Detection**: Quantile-based outlier removal for robust modeling

### 2. Statistical Testing
- **Normality Testing**: Shapiro-Wilk test for distribution assessment
- **Variance Testing**: Levene's test for equal variances across groups
- **Parametric vs Non-parametric**: Automated test selection based on data assumptions
- **Feature Significance**: Statistical validation of feature-target relationships

### 3. Data Preprocessing Pipeline

#### Feature Engineering:
- **List Feature Processing**: Handling comma-separated categorical features
- **Threshold Filtering**: Removing low-frequency categorical values
- **One-Hot Encoding**: Converting categorical variables to numerical format
- **Feature Selection**: Statistical significance-based feature filtering

#### Data Transformation:
- **Box-Cox Transformation**: Normalizing skewed distributions
- **Standard Scaling**: Z-score normalization for distance-based algorithms
- **Target Transformation**: Applying transformations to improve model performance

### 4. Machine Learning Models

#### Model Selection Framework:
The project implements a comprehensive model selection system comparing:

1. **Random Forest Regressor**
   - Ensemble method with multiple decision trees
   - Handles non-linear relationships and feature interactions
   - Robust to outliers and missing values

2. **ElasticNet Regression**
   - Linear model with L1 and L2 regularization
   - Combines Ridge and Lasso regression benefits
   - Provides feature selection and multicollinearity handling

3. **Multi-Layer Perceptron (MLP)**
   - Neural network with multiple hidden layers
   - Non-linear modeling capabilities
   - Early stopping and validation monitoring

#### Hyperparameter Optimization:
- **Grid Search**: Exhaustive search over parameter combinations
- **Cross-Validation**: 5-fold CV for robust performance estimation
- **Early Stopping**: Preventing overfitting in neural networks
- **Loss Function Monitoring**: MLP training curve analysis

### 5. Model Evaluation

#### Performance Metrics:
- **RMSE (Root Mean Square Error)**: Primary metric for regression evaluation
- **MAE (Mean Absolute Error)**: Robust error measurement
- **R² Score**: Coefficient of determination for variance explanation

#### Model Comparison Results:
- **MLP Regressor**: Selected as best model (R² = 0.58)
- **Random Forest**: Underfitting issues (R² = -1.46)
- **ElasticNet**: Performance limitations with complex feature interactions

### 6. Model Interpretation

#### SHAP Analysis:
- **Feature Importance**: Global feature contribution analysis
- **Individual Predictions**: Local explanation for specific instances
- **Summary Plots**: Visual representation of feature impacts
- **Permutation Explainer**: Model-agnostic interpretation method

#### Counterfactual Analysis:
- **DICE Integration**: Generating "what-if" scenarios
- **Feature Sensitivity**: Understanding feature change impacts
- **Business Insights**: Actionable recommendations for film production

## Technical Implementation

### Dependencies
```python
# Core Libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Machine Learning
from sklearn.ensemble import RandomForestRegressor
from sklearn.neural_network import MLPRegressor
from sklearn.preprocessing import StandardScaler, PowerTransformer
from sklearn.model_selection import GridSearchCV, cross_val_score
from sklearn.metrics import mean_squared_error, mean_absolute_error

# Statistical Analysis
from scipy import stats
from scipy.stats import boxcox

# Model Interpretation
import shap
from dice_ml import Dice, Data, Model

# Data Processing
from unidecode import unidecode
```

## Key Findings

### Model Performance:
- **Best Model**: MLP Regressor with R² = 0.58
- **RMSE**: 13.5M (on scaled data)
- **MAE**: 5.2M (on scaled data)

### Feature Insights:
- **Budget Features**: Strong correlation with opening weekend revenue
- **Director/Cast**: Significant impact on box office performance
- **Genre Effects**: Different genres show varying revenue patterns
- **Pre-production Factors**: Early indicators of commercial success

## Business Applications

This model provides valuable insights for:

### Film Industry:
- **Budget Planning**: Optimal budget allocation for maximum ROI
- **Talent Selection**: Director and cast impact on revenue
- **Genre Strategy**: Market positioning for different film types
- **Risk Assessment**: Pre-production success probability

### Investment Decisions:
- **Revenue Forecasting**: Early-stage revenue predictions
- **Portfolio Management**: Diversification across film projects
- **Market Analysis**: Understanding audience preferences

## File Structure

```
ml-basics/
├── README.md                           # This file
├── pre_production_model.ipynb         # Complete ML pipeline notebook
└── datasets/                          # Data files (if any)
```