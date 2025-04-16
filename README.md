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
    * **Name:** United States Crime
    * **Source:** Kaggle.com
    * **Link:** https://www.kaggle.com/datasets/nuritasthedataist/united-states-crime
    * **Data Acquisition Method:** Kaggle's download feature allowed me to download it as a csv file

**Dataset's Columns:**

* **U.S. Unemployment Rates:**
    * **Date:** the interval of the years are between 1948-2014 and for every month of the year
    * **overall_rate:** rate of the unemployment
    * **men_rate:** defines itself
    * **women_rate:** defines itself
    * **ages for both genders as multiple columns**

* **United States Crime:**
    * **State**: The U.S. state where the crime data was recorded.
    * **Year**: The year in which the crime data was collected.
    * **Data.Population**: Population of the state during the specified year.
    * **Data.Rates.Property.All**: Total property crime rate per 100,000 population.
    * **Data.Rates.Property.Burglary**: Burglary rate per 100,000 population.
    * **Data.Rates.Property.Larceny**: Larceny-theft rate per 100,000 population.
    * **Data.Rates.Property.Motor**: Motor vehicle theft rate per 100,000 population.
    * **Data.Rates.Violent.All**: Total violent crime rate per 100,000 population.
    * **Data.Rates.Violent.Assault**: Aggravated assault rate per 100,000 population.
    * **Data.Rates.Violent.Murder**: Murder and nonnegligent manslaughter rate per 100,000 population.
    * **Data.Rates.Violent.Rape**: Rape rate per 100,000 population.
    * **Data.Rates.Violent.Robbery**: Robbery rate per 100,000 population.
    * **Data.Totals.Property.All**: Total number of property crimes.
    * **Data.Totals.Property.Burglary**: Total number of burglaries.
    * **Data.Totals.Property.Larceny**: Total number of larceny-theft offenses.
    * **Data.Totals.Property.Motor**: Total number of motor vehicle thefts.
    * **Data.Totals.Violent.All**: Total number of violent crimes.
    * **Data.Totals.Violent.Assault**: Total number of aggravated assaults.
    * **Data.Totals.Violent.Murder**: Total number of murders and nonnegligent manslaughters.
    * **Data.Totals.Violent.Rape**: Total number of rapes.
    * **Data.Totals.Violent.Robbery**: Total number of robberies.


**Data Collection and Preparation:**

The datasets were obtained from Kaggle. Python Libraries will be used on these data like pandas, matplotlib, seaborn, scikit-learn. The data will undergo the following preparation steps:

* **Data Cleaning:** 
    * Missing Values: Rows with missing values in relevant columns will be removed.
    * Inconsistent Formatting: Any inconsistencies in data formatting will be addressed through standardization.
     * All relevant columns, including violent crime breakdowns (murder, rape, robbery, etc.), are retained for deeper analysis and future modeling, however states columns will be disregarded.
* **Data Transformation:**
    * Aggregation: Both the unemployment and crime datasets are grouped by year to create national-level annual summaries.
        - The unemployment dataset is averaged per year.
        - The crime dataset is summed across all states per year.
    * Column Renaming: Final columns are standardized to `Year`, `UnemploymentRate`, and `CrimeCount` for clarity.
    * Type Checking: All numeric columns are verified and cast as appropriate numeric types.
* **Data Integration:** 
    The two datasets are merged using the `Year` column as the key. This produces a single, unified dataset suitable for time-series analysis, hypothesis testing, and future machine learning tasks.

**Analysis Plan:**

1. **Exploratory Data Analysis (EDA):**

   The EDA aims to deeply understand the relationship between national United States unemployment and crime rates across years. The steps include:

   * **Summary Statistics:**
     - Mean, median, standard deviation, min, max for both `UnemploymentRate` and `CrimeCount`.
     - Year-over-year percent change for both metrics.
     - Skewness to understand distribution shape.

   * **Correlation Matrix:**
     - Heatmap visualization of correlations between numerical columns.

   * **Visualizations:**
     - **Line Plot** showing annual trends for `UnemploymentRate` and `CrimeCount`.
     - **Scatter Plot** of `UnemploymentRate` vs. `CrimeCount` to observe the relationship.
     - **Box Plots** for both variables to inspect spread and outliers.
     - **Bar Chart** showing total crimes per year.
     - **Histogram** for each variable to assess distribution shape.

2. **Hypothesis Testing:**

   A **Pearson correlation test** will be used to evaluate whether there is a statistically significant linear relationship between unemployment rate and crime rate.

   * **Null Hypothesis (H₀):** There is no statistically significant correlation between unemployment rates and crime rates in the US.
   * **Alternative Hypothesis (H₁):** There is a statistically significant correlation between unemployment rates and crime rates in the US.

   * **Test Details:**
     - **Test Used:** Pearson correlation coefficient
     - **Test Statistics:** Correlation coefficient (r), p-value
     - **Significance Level (α):** 0.05
     - **Degrees of Freedom (df):** *n - 2*, where *n* is the number of yearly observations

   The result will indicate the strength and significance of the relationship. If the p-value is less than 0.05, we reject the null hypothesis and conclude that a statistically significant relationship exists.

3. **Visualization Summary:**

   The following plots will be generated to aid interpretation:

   * **Line Plot** – Trends over years for both `UnemploymentRate` and `CrimeCount`
   * **Scatter Plot** – Relationship between `UnemploymentRate` and `CrimeCount`
   * **Correlation Heatmap** – Overview of all numerical relationships
   * **Box Plots** – Distribution and outliers in both metrics
   * **Histograms** – Frequency distribution of each metric
   * **Bar Chart** – Total crime per year

**Trend Analysis:**

Trends in both unemployment rates and crime counts will be analyzed over time using line plots and year-over-year change graphs. This allows us to identify potential long-term patterns, parallel movements, or divergences between the two variables. We will explore:

* Whether crime rates increase or decrease during years of rising unemployment.
* Any lagged effects — for example, if unemployment spikes are followed by increases in crime the next year.
* General direction of each metric (increasing, decreasing, or cyclical trends).
* Any noticeable outliers or anomalies in specific years that deviate from the general pattern.

This trend analysis will provide context for the hypothesis testing and guide future modeling steps, such as considering lag variables or non-linear models.

**Technology Stack:**
* Python
* Pandas
* Matplotlib
* Seaborn (Optional)
* scikit-learn
* scipy

**Timeline:**

* **March 14, 2025:** Project Proposal Submission (This README file)
* **April 25, 2025:** Exploratory Data Analysis and hypothesis tests on the data
* **May 23, 2025:** Apply ML methods on the dataset
* **May 30, 2025:** Final Report Submission


**Team:** Abdallah Al Homsi (Individual Project)
**Student ID** 34565

