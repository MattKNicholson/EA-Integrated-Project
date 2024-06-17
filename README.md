# EA Integrated Project

## Overview

This project analyzes an insurance claims dataset from the American insurance market using Excel, Python, and Power BI to uncover trends and insights. The project follows five distinct phases:

1. Data Cleansing
2. Data Exploration
3. Feature Engineering and Extraction
4. Data Modeling
5. Visualization in Power BI

## 1. Data Cleansing

### 1.1 Excel

- **File**: `1_insurance_claims_raw.xlsx`
- The raw insurance claims data is stored in this file and remains untouched to preserve a clean copy for reference.
- **Cleansing Process**:
  - Replaced null values with appropriate mean/median/mode values for numerical and categorical data using Excel processes.
  - Conducted analysis using pivot tables to assign the most appropriate values.
  - For some categorical data, such as `Police_Report`, where imputing the mode value was inappropriate, "unknown" was input instead.
  - All manual imputations are recorded in the "imputations" tab.
- **Output**: `2_insurance_claims_clean.xlsx`

### 1.2 Python

- Using a Jupyter Notebook and Python, the data is further checked for missing/null values.
- Data types are cleansed for additional analysis, feature engineering, and model generation using Python libraries.

## 2. Data Exploration

- Utilized Python libraries to explore the cleansed dataset.
- Functions like `describe` and `info` are used to understand the dataset's structure and ensure data integrity.
- Identified immediate standout statistics and verified data formats across all fields.

## 3. Feature Engineering and Extraction

### 3.1 Creating Additional Features

- **Age Groupings**: Explored via graphical analysis and created "age bins" for further analysis.
- **Derived Fields**: Extracted year, month, and day from the `incident_date` field.

### 3.2 Calculating Numerical Fields

- Created a new `fraudulent_claims_amount` field by combining `total_claims_amount` values where `fraud_reported` is 'y'. This reduces processing time and complexity in the Power BI dashboard.

### 3.3 External Data Integration

- Incorporated external data from Forbes.com to highlight fraud as a major concern in the American insurance industry. Evidence is included in the Jupyter notebook.

### 3.4 Graphical Analysis

- Analyzed the `fraudulent_claims_amount` column against key fields using histograms, pair plots, and bar charts to identify trends and insights.

## 4. Data Modeling

- **Objective**: Identify and reduce potential fraud.
- **Approach**:
  - Built a model to predict if an existing client poses a fraud risk.
  - Applied one-hot encoding for categorical features and scaled numerical features.
  - Identified the top 10 correlated features to the `fraud_reported_y` column.
  - Implemented a Random Forest classifier to predict fraudulent claims.
  - Evaluated model performance using a confusion matrix, classification report, and accuracy score on the train/test dataset.

## 5. Visualization in Power BI

- Developed a Power BI dashboard to provide end users with data insights and enable visual data discovery.

### 5.1 Fraudulent Claims Analysis

- Focuses on highlighting primary trends in fraudulent claims.
- **Features**:
  - Filters for year, sex, policy state, and age group.
  - KPIs on the left side for high-level statistics.
  - Pie charts, bar charts, and combo charts to emphasize key fields related to fraud.

### 5.2 Fraudulent Claims Detail

- Offers a detailed view of selections made in the 'Fraudulent Claims Analysis' tab.
- Allows users to delve deeper into the data behind identified trends.

     Filters have been utilised at the top right of the screen to allow the use to select a specifci year, sex, policy state and\or age group to focus in on.
     KPIs have been included down the left hand side of the tab to draw the users eye to high level stats
     Pie charts, bar and combo charts have then been used in the centre of the tab to focus the user on primary fields related to fraud as identified in the Jupyter        notebook.

  **2.  Fraudulent Claims Detail**

    This tab allows the user to see a deeper level of detail on selections that have made in the 'Fraudulent Claims Analysis' tab. This allows the oppotunity for          the user to dealve deeper into the detail behind the trends that have been identified in the previous tab.
