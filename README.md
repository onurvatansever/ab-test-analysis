# ab-test-analysis

This project analyzes an A/B test comparing a **new landing page** against an **old landing page** to determine whether the new design improves conversion rate.

## Project Overview

The notebook:
- loads the A/B test dataset
- inspects the data structure
- encodes categorical variables
- removes inconsistent rows
- removes duplicate users
- visualizes conversion performance
- runs statistical significance tests

## Dataset

The analysis uses `ab_data.csv`, which contains:

- `user_id` — unique user identifier
- `timestamp` — time of the visit
- `group` — control or treatment group
- `landing_page` — old page or new page
- `converted` — whether the user converted (`1`) or not (`0`)

## Workflow

### 1. Load Libraries
The notebook uses:
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scipy.stats`
- `statsmodels.stats.proportion`

### 2. Load Data
The dataset is read directly from GitHub.

### 3. Data Cleaning
The notebook performs the following cleaning steps:
- one-hot encodes `landing_page` and `group`
- filters out mismatched rows where the assigned group does not match the landing page
- removes duplicate users

### 4. Exploratory Analysis
The notebook compares:
- conversion rates for the new vs. old page
- number of conversions in each group

### 5. Statistical Testing
The following tests are applied:
- **Two-proportion z-test**
- **Chi-square test**

These tests help determine whether any observed difference in conversion rates is statistically significant.

## Main Question

Does the **new landing page** increase conversion compared to the **old landing page**?

## How to Run

1. Clone the repository.
2. Open `analiz.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
3. Run the notebook cells from top to bottom.

## Requirements

Install the following Python packages:

```bash
pip install numpy pandas matplotlib seaborn scipy statsmodels
