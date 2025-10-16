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

## 🔭 Future Homeworks
- **Homework 3**: [To be added]  
- **Homework 4**: [To be added]