# Unemployment-and-Crime-Rates

**Project Description:**
This project examines the dynamic relationship between unemployment and crime rates in the US, leveraging analysis.  We will utilize publicly available datasets covering a substantial time period to analyze the temporal patterns in both variables.  Statistical modeling techniques, including potential time-series regression, will be applied to identify their relationship, causes and explore potential causal links between fluctuations in unemployment and subsequent changes in crime rates.

**Motivation:**
I am motivated to undertake this project because of my strong interest in applying data science to real-world problems, particularly those with significant social impact. The complex relationship between unemployment and crime rates provides a compelling context for utilizing my developing skills in time-series analysis and statistical modeling.  I am eager to explore potential causal relationships and contribute to a deeper understanding of this important socioeconomic issue.

**Datasets:**

* **Dataset 1: Unemployment Rate Data**
    * **Name:** U.S. Unemployment Rates
    * **Source:** Kaggle.com
    * **Link:** https://www.kaggle.com/datasets/guillemservera/us-unemployment-rates
    * **Data Acquisition Method:** Exported the dataset as a zip file from kaggle's download feature and then extracted it as a csv file


* **Dataset 2: Crime Rate Data**
    * **Name:** US Crime Data
    * **Source:** Kaggle.com
    * **Link:** https://www.kaggle.com/datasets/johnybhiduri/us-crime-data
    * **Data Acquisition Method:** Exported the dataset as a zip file from kaggle's download feature and then extracted it as a csv file

**Dataset's Columns:**

* **U.S. Unemployment Rates:**
    * **Date:** the interval of the years are between 1948-2014 and for every month of the year
    * **overall_rate:** rate of the unemployment
    * **men_rate:** defines itself
    * **women_rate:** defines itself
    * **ages for both genders as multiple columns**

* **US Crime Data:**
    * **Date:** the exact time of the crime committed
    * **Title:** the incident of the crime committed
    * **Organization:** the group or individual that shared the news about the crime committed
    * **City:** which city in the US
    * **State:** which state in the US
    * **URL:** link of the news
    * **Keyword:** Keyword of the news , used to search the news
    * **Summary:** Full Summary of the News


**Data Collection and Preparation:**

The datasets were obtained from Kaggle. Python Libraries will be used on these data like pandas, matplotlib, seaborn, scikit-learn. The data will undergo the following preparation steps:

* **Data Cleaning:** 
    * Missing Values: Rows with missing values in relevant columns will be removed.
    * Inconsistent Formatting: Any inconsistencies in data formatting will be addressed through standardization.
    * Unnecessary Columns: The 'URL', 'Keyword', 'Summary', 'State', 'City', and 'Organization' columns will be removed from the crime dataset and maybe other columns to streamline the data and improve efficiency.  These columns are not necessary for the analysis.
* **Data Transformation:**
    * Date Standardization: Dates will be converted to a consistent format (YYYY-MM-DD).
    * Data Type Verification: Data types for all numerical columns will be verified and converted if necessary (e.g., ensuring that unemployment and crime rates are numerical).
    * Lagged Unemployment: New columns will be created in the crime dataset to represent lagged unemployment rates (e.g., unemployment rate from the previous month and previous year).
* **Data Integration:** The cleaned and transformed datasets will be merged using the 'Date' and location (State or County) as matching criteria. This will create a single dataset suitable for analysis.

**Analysis Plan:**

1. **Exploratory Data Analysis (EDA):**

   * The analysis will begin with EDA to gain insights into the data.  We will examine the distributions of unemployment rates and crime rates over time.
   * Summary statistics (mean, median, standard deviation, min, max, etc.) will be calculated for both variables to provide an overall understanding of their central tendency and variability.
   * Histograms and box plots will be generated to visualize the distributions and identify any potential outliers or skewness in the data.
   * Line graphs will be used to display the trends in unemployment rates and crime rates over time, allowing us to identify any potential patterns or correlations visually.

2. **Hypothesis Testing:**

   The following hypotheses will be tested to determine if there is a statistically significant correlation between unemployment rates and crime rates:

   * **Null Hypothesis (H₀):** There is no statistically significant correlation between unemployment rates and crime rates in the US.
   * **Alternative Hypothesis (H₁):** There is a statistically significant correlation between unemployment rates and crime rates in the US.

3. **Visualization:**

   The following visualizations will be created:

   * Line graphs displaying the trends in unemployment rates and crime rates over time, allowing for a visual comparison of their patterns.
   * Scatter plots showing the relationship between crime rates and unemployment rates, potentially using lagged unemployment variables to assess the predictive power of past unemployment.

**Trend Analysis:**

Line graphs will be used to visualize trends in unemployment and crime rates. We will investigate correlations, potential seasonality, and time lags between changes in the two variables.

**Technology Stack:**
* Python
* Pandas
* Matplotlib
* Seaborn (Optional)
* scikit-learn

**Timeline:**

* **March 14, 2025:** Project Proposal Submission (This README file)
* **April 18, 2025:** Exploratory Data Analysis and hypothesis tests on the data
* **May 23, 2025:** Apply ML methods on the dataset
* **May 30, 2025:** Final Report Submission


**Team:** Abdallah Al Homsi (Individual Project)
**Student ID** 34565

