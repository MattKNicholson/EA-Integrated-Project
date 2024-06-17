**EA Integrated Project**

This project analyses an insurance claims dataset based on the American insurance market using Excel, Python and Power BI to expose trends and insights.

The project follows five distinct phases:

**1.0 Data cleansing**

**1.1 Excel**

The initial "insurnace_claims" data has been downloaed and stored as "1_insurance_claims_raw.xlsx". This subsequently remains untouched in order that we always have a clean copy of the source data to revert and recocnile to if needs be
The "raw" data is then initially cleansed via Excel processes to replace null values with appropirate mean/median/mode values for missing numerical and categorical data. Additional analysis using pivot tables has also been implemented in order to assign the most appropriate value.

There are instances with missing categorical data where it appears inappropriate\inaccriate to replace null entries with the mode value, i.e. Police_Report. Here, an entry of "unknown" has been input.
All manual imputatiosn have been recorded in the "imputations" tab for reference
Once cleanesed, this Excel file has been saved as "2_insurance_claims_clean.xlsx"

**1.2 Python**

Using a Jupyter Notebook and Python, the data is then further checked for missing\null values and the data types cleansed further for additional analysis, feature engineering and model generation using Python libraries.

**2.0 Data exploration**

Using Python libraries, we are able to explore the cleansed dataset to understand the make up and context of the data as we search for trends, patterns and potential causes for concern with the data captured.

We can look for any immediate stand out statistics via the "describe" function and ensure that all data is in an appriate format by using the "info" function across all data fields.

**3.0  Feature engineering and extraction**

Here we seek to dig further into the data to begin to extract insights.

**3.1** The creation of additional features such as age groupings, where are firstly explored via graphical analysis and then acted upon through creating "age bins" for onward analysis.
Year, month and day fields are dervived via the 'incident_date' field.

**3.2** Additional numerical value fields are calculated and created through joining existing data fields together, i.e. a new 'fraudlent_claims_amount' field is calculated by pulling through the 'total_claims_amount' values where the 'fraud_reported' column is equal to 'y'. This saves processing time and complexity further down the line in the Power BI dashboard.

**3.3**  I have then used additional external courses of data, Forbes.com, to indentify that fraud is a major area of concern within the American insurance industry - see images that have been bought through into the Jupyter notebook as evidence.

**3.4**   With that in mind, graphical analysis of the new 'fraudlent_claims_amount' column has been run against other key fields to see if trends \ insights can be identified - see histogram, pairplot and bar charts in the notebook
    
**4.0  Data modeling**

At this point, we have determined that the idientofical and reduction of potential fraud is the problem that we are aiming to solve.

It is therefore appropriate that we should now attemp to build a model that would help an insurance firm model as to whether an existing client is a fraud risk. Using oen hot encoding for categorical features, scaled of numerical features, I have first sought to identiofy the top 10 correlated features to the 'fraud_reported_y' column.

Using these 10 features, the random forest classifier is initialised and run against the reduced feature set to predict the liklihood of a client making a fraudulent claim.

A subsequent confusion matrix, classification report and accuracy score is calculated to analyse the efffectiveness of the model on the train\test dataset.

**5.0 Visualisation in Power BI**

Having cleansed the data, run feature extraction and feature engineering across the data, identiying that Fraud Reduction is our aim and creating a predictive fraud model, our next step is to build a Power BI dashboard for end users to gain data insights and bring about data discovery visually.

The Power BI dashboard contains two tabs:

 **1. Fraudulent Claims Analysis**
 
     Here, the focus is only drawing attenion to the primary trends where a fraudulent claim has been made. Standard cliam amounts have been excluded from this             dashboard as we want full focus on the fraudulent claims and therefore want to remove any other "noise" from this specific dashboard
     Filters have been utilised at the top right of the screen to allow the use to select a specifci year, sex, policy state and\or age group to focus in on.
     KPIs have been included down the left hand side of the tab to draw the users eye to high level stats
     Pie charts, bar and combo charts have then been used in the centre of the tab to focus the user on primary fields related to fraud as identified in the Jupyter        notebook.

  **2.  Fraudulent Claims Detail**

    This tab allows the user to see a deeper level of detail on selections that have made in the 'Fraudulent Claims Analysis' tab. This allows the oppotunity for          the user to dealve deeper into the detail behind the trends that have been identified in the previous tab.
