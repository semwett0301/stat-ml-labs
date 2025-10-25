# Statistics Course - ITMO University

This directory contains coursework from ITMO University's statistics course, focusing on mathematical statistics and statistical analysis techniques.

## Course Overview

This course covers fundamental concepts in mathematical statistics, including:
- Introduction to Mathematical Statistics
- Types of Statistical Estimates and Characteristics
- Statistical Analysis and Data Visualization
- Hypothesis Testing and Correlation Analysis

## Homeworks Structure

The course consists of **4 homeworks**, each containing a set of exercises that require analytical solutions and statistical computations.

## 📊 Homework 1: Statistical Characteristics and Estimations

**File**: `math_stat_1.ipynb`  
**Topics**: Introduction to Mathematical Statistics and Types of Statistical Estimates  

### Dataset
- **Anime Dataset**: Contains 10,486 anime records with features including:
  - `anime_id`: Unique identifier
  - `name`: Anime title
  - `genre`: Genre(s) (comma-separated string)
  - `type`: Format (TV, Movie, OVA, etc.)
  - `episodes`: Number of episodes
  - `rating`: Average rating
  - `members`: Number of viewers
  
### Technologies Used
- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn
- **Statistical Analysis**: Descriptive statistics, correlation analysis, anomaly detection

## 📈 Homework 2: Confidence Intervals

**File**: `math_stat_2.ipynb`  
**Topics**: Confidence intervals for means and proportions; comparison across groups  

### Outline
- Build CIs for a population mean with known variance (z-interval).  
- Build CIs for a population mean with unknown variance (t-interval).  
- Build CIs for a population proportion.  
- Apply CIs to real datasets to compare categories and groups (width analysis, group with widest/narrowest CI, etc.).

### Datasets
- **Anime Dataset** (`anime.csv`): Same schema as in Homework 1 (downloaded in notebook).  
  Used to compute 95% CIs for ratings overall, by genre (e.g., comedy), and by type (e.g., Movie), and to analyze CI widths across categories; also tasks on episodes and members.
- **Customer Shopping Data** (`customer_shopping_data.csv`): Contains retail transactions with fields:  
  - `invoice_no`, `customer_id`, `gender`, `age`, `category`, `quantity`, `price`, `payment_method`, `invoice_date`
  Used to compute 95% CIs for average age, average check (`quantity * price`) overall and by payment method/category, daily customer counts, and differences between groups (e.g., men vs women).

### Technologies Used
- **Computation**: numpy, pandas, scipy.stats
- **Visualization**: matplotlib, seaborn

## 🧪 Homework 3: Hypothesis Testing

**File**: `math_stat_3.ipynb`  
**Topics**: Statistical hypothesis testing, z-tests, t-tests, and proportion tests

### Outline
This homework covers fundamental hypothesis testing concepts including:
- **Z-tests**: Testing population means with known variance
- **T-tests**: Testing population means with unknown variance (one-sample and two-sample)
- **Proportion tests**: Testing population proportions using normal approximation
- **Statistical power analysis**: Calculating power and Type II error rates
- **Critical value calculations**: Determining rejection regions and critical sample sizes

### Key Statistical Concepts Covered
- **One-tailed vs Two-tailed tests**: Understanding directional vs non-directional hypotheses
- **P-value calculations**: Computing probabilities under null hypothesis
- **Effect size and power**: Analyzing test sensitivity and sample size requirements
- **Independent samples t-test**: Comparing means between two groups
- **Paired samples**: Analyzing differences within the same subjects

### Problem Types
1. **Z-test problems**: Population mean testing with known variance
2. **One-sample t-tests**: Population mean testing with unknown variance
3. **Two-sample t-tests**: Comparing means between independent groups
4. **Proportion tests**: Testing population proportions (e.g., success rates)
5. **Power analysis**: Calculating statistical power and required sample sizes
6. **Critical value determination**: Finding rejection thresholds

### Technologies Used
- **Statistical Computing**: scipy.stats (norm, t, binom distributions)
- **Numerical Analysis**: numpy for mathematical operations
- **Visualization**: matplotlib for plotting distributions and test statistics
- **Statistical Functions**: Built-in functions for CDF, PDF, and inverse CDF calculations

## 🔭 Future Homeworks
- **Homework 4**: [To be added]