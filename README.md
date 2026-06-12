# 🚲 Bike Rental Demand Analysis

An end-to-end exploratory data analysis and predictive modeling project examining what drives bike-sharing demand across seasons, hours, and weather conditions.

---

## Overview

This project analyzes hourly bike rental records to uncover the behavioral and environmental patterns behind rider demand. Using descriptive statistics, visualization, and linear regression, the analysis answers three core questions:

1. **When do people rent bikes?** — How does demand shift across hours of the day and months of the year?
2. **What environmental conditions drive rentals?** — How do temperature, humidity, and wind affect demand?
3. **Can demand be predicted?** — How well does a linear regression model estimate rental counts from weather and time features?

---

## Key Findings

- **Rentals peak at rush hours** (8 AM and 5–6 PM), strongly suggesting commuter usage alongside recreational riding.
- **Summer months drive the most rentals**, with demand roughly doubling compared to winter months.
- **Temperature has the strongest positive correlation** with rental count among individual features, though the relationship is non-linear.
- **A multivariable linear regression** using temperature, humidity, windspeed, month, and hour explains general demand trends but shows meaningful dispersion — indicating that non-linear models would likely perform better.

---

## Project Structure

```
bike-rental-analysis/
│
├── bike_rental_analysis.ipynb   # Main analysis notebook
├── README.md                    # This file
└── data/
    ├── bikes_final.csv          # Hourly bike rental dataset
    └── bike_metadata.xlsx       # Variable descriptions
```

---

## Dataset

The dataset contains hourly bike rental counts from a Washington D.C. bike-share system, along with weather and calendar information.

| Feature | Description |
|---|---|
| `datetime` | Hourly timestamp |
| `season` | 1=Spring, 2=Summer, 3=Fall, 4=Winter |
| `holiday` | Whether the day is a holiday |
| `workingday` | Whether the day is a working day |
| `weather` | Weather condition (1=Clear → 4=Heavy Rain) |
| `temp` | Normalized temperature in Celsius |
| `humidity` | Relative humidity |
| `windspeed` | Normalized wind speed |
| `count` | Total bike rentals (target variable) |

---

## Methods

| Stage | Techniques |
|---|---|
| Data Cleaning | Datetime parsing, feature extraction (month, hour) |
| Descriptive Statistics | `.describe()`, `value_counts()`, correlation matrix |
| Visualization | Histograms, bar charts, line plots, scatter plots |
| Feature Engineering | Extracted `month` and `hour` from `datetime` |
| Regression | `sklearn` `LinearRegression` — simple (temp only) and multivariable |
| Code Quality | Reusable `format_plot()` helper function |

---

## Setup

```bash
# Clone the repo
git clone https://github.com/yourusername/bike-rental-analysis.git
cd bike-rental-analysis

# Install dependencies
pip install pandas matplotlib scikit-learn openpyxl

# Launch the notebook
jupyter notebook bike_rental_analysis.ipynb
```

**Python version:** 3.8+  
**Dependencies:** `pandas`, `matplotlib`, `scikit-learn`

---

## Sample Visualizations

The notebook includes:
- Distribution of bike rentals (histogram)
- Average rentals by month (bar chart)
- Average rentals by hour of day (line chart)
- Temperature vs. rentals (scatter plot with regression line)
- Actual vs. predicted rentals (multivariable model)

---

## Limitations & Future Work

- The linear regression model assumes linearity, but the temperature–rentals relationship curves at high temperatures. A **polynomial regression** or **random forest** model would likely improve fit.
- Categorical variables (season, weather condition, day of week) were excluded from the regression model. Including them as encoded features could improve predictive accuracy.
- The dataset represents a single city (D.C.) — results may not generalize to other markets.

Future directions could include ensemble models (gradient boosting), time-series forecasting (ARIMA / Prophet), and interactive dashboards with Plotly or Streamlit.

---

## About

This project was completed as part of a data analytics course. It demonstrates proficiency in Python-based EDA, data visualization, feature engineering, and predictive modeling.

**Tools:** Python · pandas · matplotlib · scikit-learn · Jupyter
