# Unemployment-and-Crime-Rates

## **Project Description:**
This project explores the relationship between unemployment and crime rates in the United States from both a statistical and machine learning perspective. Using multi-decade, real-world datasets, the project investigates how economic factors, particularly unemployment, may influence crime patterns.

We aim to answer the question: "Do higher unemployment rates contribute to higher crime rates?" To do so, we perform end-to-end data analysis—starting from raw data cleaning and transformation to hypothesis testing and predictive modeling using classification and regression algorithms.

- [Final Report](https://docs.google.com/document/d/1LPHQpYV3Q2kSO_xjkDGIbCx-m6Z3jcVzorBfDrT5buk/edit?usp=sharing)

## **Motivation:**
The relationship between economic hardship and crime has long been studied in sociology and criminology. As a data science enthusiast with a passion for impactful social issues, I am driven to explore this question using rigorous, data-driven approaches. Understanding this link can help governments and organizations allocate resources more effectively, develop better prevention policies, and forecast crime trends based on economic indicators.

## **Datasets:**

### * **Dataset 1: Unemployment Rate Data**
    * **Name:** U.S. Unemployment Rates
    * **Source:** Kaggle.com
    * **Link:** https://www.kaggle.com/datasets/guillemservera/us-unemployment-rates
    * **Data Acquisition Method:** Exported the dataset as a zip file from kaggle's download feature and then extracted it as a csv file

### * **Dataset 2: Crime Rate Data**
    * **Name:** United States Crime
    * **Source:** Kaggle.com
    * **Link:** https://www.kaggle.com/datasets/nuritasthedataist/united-states-crime
    * **Data Acquisition Method:** Kaggle's download feature allowed me to download it as a csv file

### * **Datasets 3 and 4: Enrichment Datasets** 
    * **admissions.csv and salary_bras.csv (added for ML enhancement)**
    * **Purpose:** Enhance socioeconomic context and improve prediction models by adding auxiliary variables like salary distributions and prison admissions.

## **Data Collection and Preparation**

### **1. Data Cleaning**
- Converted dates to datetime format.
- Extracted `Year` column from timestamps.
- Dropped rows with missing values in key columns.
- Removed outliers and rows with obviously incorrect or zero values (e.g., 0 crime counts in states with high population).

### **2. Aggregation & Integration**
- **Unemployment:** Aggregated monthly data into yearly national averages.
- **Crime:** Grouped by year and averaged across all 50 states to get national-level indicators.
- Merged datasets using `Year` as the common key.

### **3. Feature Engineering**
- Created a `TotalCrimeRate` column by summing `Data.Rates.Property.All` and `Data.Rates.Violent.All`.
- Calculated year-over-year percentage changes: `Unemp_YoY_%` and `Crime_YoY_%`.
- Introduced binary and multiclass categorical targets for classification (e.g., `DominantNextCrimeType`).
- Normalized numeric columns and encoded categorical ones for modeling purposes.

### **4. Data Enrichment**
- Integrated additional datasets (`admissions.csv`, `salary_brackets.csv`) to include economic and social indicators.
- Merged on shared keys such as state/year where appropriate.
- Resulted in more comprehensive socioeconomic context for machine learning models.

## **Analysis Plan:**

### **1. Exploratory Data Analysis (EDA)**
- Displayed summary statistics and distributions of all core features.
- Used `.describe()` and `.skew()` to understand spread and symmetry.
- Generated correlation matrix and heatmaps.
- Created the following plots:
  - Line plots for `UnemploymentRate` and `TotalCrimeRate` over time.
  - Year-over-year trend analysis.
  - Scatter plots to observe linear relationships.
  - Histograms and boxplots for distribution analysis.

 **Key Insights:**
- Total crime rate peaked in the 1990s and declined thereafter.
- Unemployment fluctuates in cycles (recession-related), not strictly aligned with crime.
- Positive correlations between unemployment and crime types such as larceny, robbery, and assault.

### **2. Hypothesis Testing**

 **Hypothesis:**
- **H₀ (Null):** There is no statistically significant correlation between unemployment and crime.
- **H₁ (Alternative):** There is a significant correlation between unemployment and crime.

**Method:**
- Used the **Pearson correlation coefficient** to test the relationship between:
  - `UnemploymentRate` and `TotalCrimeRate`

**Results:**
- Pearson r ≈ **0.28**, p-value ≈ **0.0327**
- Rejected the null hypothesis at α = 0.05 level.
- Weak to moderate positive correlation → unemployment is **statistically associated** with crime, though not strongly.

## **Machine Learning Models**

### **1. Classification (Random Forest)**
- **Target:** `DominantNextCrimeTypeMulti` (most frequent crime type next year)
- **Features Used:**
  - Socioeconomic features (from enrichment datasets)
  - Crime subcategories (excluding `.All` aggregates and future-leaky columns)
- **Preprocessing:**
  - Label encoding of target.
  - SMOTE oversampling (`sampling_strategy='not majority'`) to balance minority classes.
  - Removed duplicate and missing rows.
- **Model:** `RandomForestClassifier(n_estimators=120, max_depth=14, min_samples_leaf=8)`
- **Accuracy:** **94%**
- **Classification Report Highlights:**
  - High precision and recall for major classes (e.g., Larceny, Murder, Burglary)
  - Model generalizes well on unseen data

### **2. Regression (Linear Regression)**
- **Target:** `Data.Rates.Violent.All` (total violent crime rate)
- **Features:** Purely socioeconomic, removing all crime-related features to prevent leakage
- **Model:** `LinearRegression()`
- **Metrics:**
  - **R² Score:** 0.83
  - **MAE:** 49.7
  - **MSE:** 5440.58
- **Top Predictive Features:** Extracted and ranked by coefficient magnitude
- **Visualization:** Actual vs Predicted scatter plot confirms good model

## **Limitations and Future Work**

### **Limitations**
- Aggregating state data into national averages may hide local trends.
- Models do not account for time-lag effects or deep temporal patterns.

### **Future Work**
- Explore regional analysis
- Add more features (e.g., education, income inequality) to improve predictions.
- Use causal inference methods to better understand relationships.

## **Technology Stack:**
- **Languages:** Python  
- **Libraries:** pandas, matplotlib, seaborn, scikit-learn, imbalanced-learn, scipy  
- **Tools:** Jupyter Notebook, VSCode, GitHub

## **Timeline:**

| Task                            | Deadline         |
|---------------------------------|------------------|
| Project Proposal Submission     | March 14, 2025   |
| EDA & Hypothesis Testing        | April 25, 2025   |
| Machine Learning Modeling       | May 23, 2025     |
| Final Report Submission         | May 30, 2025     |


## **Team:** Abdallah Al Homsi (Individual Project)
## **Student ID** 34565

