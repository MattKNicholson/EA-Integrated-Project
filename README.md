# EA Integrated Project - Fraudulent Claims Analysis

## Overview

This project analyses an insurance claims dataset from the American insurance market using Excel, Python, and Power BI to uncover trends and insights into fraudulent claims. 

The aim of the project is to analyse this specific data set, drawing out key issues impacting the insurance market and defining a problem that this project can seek to address.

The data cleansing in both Excel and Python, the outside reaesrch using Forbes, python feature engineering and subsequent graphical anaylsis in Jupyter notebooks has bought insights into the significant issues that fraudulent claims have upon the insurance market. The problem definition of this project is therefore; to suport the identification of potential fraudlent policy profile types to enable the insurance firm to address these within their current book of business and also as a screening methdology when onboarding new clients.

A key issue in the African insurance market is to increase the number of people taking out insurance policies. However, it will be vital that the screening processes are in place to flag potential fraudlent profiles during the onboarding process and to then enact approriate action for the business to take further screening steps on specific profile types in ordre to reduce the risk of future fraud.

To that end a ML random forest modle has also been developed in the Jupyter notebook as a prototype to run again both the current book of business and as a screening tool when onboarding new clients.

It must be noted that this dataset is limited to a narrow date range and to only those policy holders that have made a claim. This data set excludes policy holders that have not made a claim and therefore it is impossible to run an appropriate analysis on "value" since we do not have a full set of data to include premiums paid by policy holders that have not made a claim in this data period.

The project follows five distinct phases:

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

- Utilised Python libraries to explore the cleansed dataset.
- Functions like `describe` and `info` are used to understand the dataset's structure and ensure data integrity.
- Identified immediate standout statistics and verified data formats across all fields.

## 3. Feature Engineering and Extraction

### 3.1 Creating Additional Features

- **Age Groupings**: Explored via graphical analysis and created "age bins" for further analysis.
- **Derived Fields**: Extracted year, month, and day from the `incident_date` field.

### 3.2 Calculating Numerical Fields

- Created a new `fraudulent_claims_amount` field by combining `total_claims_amount` values where `fraud_reported` is 'y'. This reduces processing time and complexity in the Power BI dashboard.
- Created additional metrics: Annual claim net value, total premium amount metrics calculated to look at "value" creation per policy holder.  

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
- See the Power BI dashboard included in this repo along with the images within the "image" folder for a quick view of the dashboard tabs.

### 5.1 Fraudulent Claims Analysis

- Focuses on highlighting primary trends in fraudulent claims.
- **Features**:
  - Filters for year, sex, policy state, and age group.
  - KPIs on the left side for high-level statistics.
  - Pie charts, bar charts, and combo charts to emphasise key fields related to fraud.

### 5.2 Fraudulent Claims Analysis2

- The dashboard in 5.2 identifies that a major relationship in the fraudulent claims is on the "incident severity" type. Drilling further into that, we can then look at the "collision type", the "top 10" policies makin fraudulent claims and also the location of the incident. This may pull out additional opportunities for data discovery and garner further insights into fraudulant policy holder profiles.
- **Additional Features**:
  - Analysis of claims by collision type
  - Analysis of claims by incident city
  - Table showing the top 10 fraudulent claims by policy holder based upon filter options selected

### 5.3 Fraudulent Claims Detail

- Offers a detailed view of selections made in the 'Fraudulent Claims Analysis' tab.
- Allows users to delve deeper into the data behind identified trends.
