# Air-Toxin-Cancer-vs-Demographics-Analysis

## Introduction
___________________________________________
The rise in global cancer incidences is a matter of considerable concern, especially when taking into account the role that environmental factors play in its propagation. Air toxins in particular have been identified as a key environmental risk factor. Demographic elements such as income, education, language proficiency, and age distribution often affect a population's vulnerability to these toxins. Therefore, this study aims to create a visualization highlighting cancer risk as it relates to air toxins, taking into account these demographic vulnerability markers. This project has significant potential to inform policy decisions and guide strategies intended to reduce cancer prevalence in communities at high risk.

# Objectives
___________________________________________
    The primary objectives of this analysis are:

1.  To delineate the relationship between air toxins, cancer occurrences, and diverse demographic aspects.
2.  To identify demographic groups that are most susceptible to cancer due to air toxins.
3.  To project future trends concerning cancer incidences in relation to air toxins and demographic susceptibility.
4.  To propose strategies for reducing cancer risks associated with air toxins in vulnerable communities, based on the findings of this study.

## Dataset
___________________________________________
   The data utilized in this study originates from the Environmental Justice (EJ) Screen dataset, accessible on the EPA's website. Essential variables include total cancer cases (tot_can), percentage of minority population (MINORPCT), percentage of low-income population (LOWINCPCT), percentage of population with less than high school education (LESSHSPCT), percentage of linguistically isolated population (LINGISOPCT), percentage of population under 5 years old (UNDER5PCT), and percentage of population over 64 years old (OVER64PCT). These variables have been chosen based on their relevance to the study's aim of examining the interplay between air toxins, cancer risk, and demographic vulnerability.
   
## Tools and Librries Used
___________________________________________
- Programming Language: R
- Data Wrangling: dplyr
- Data Visualization: ggplot2, corrplot
- Statistical Analysis and Machine Learning: stats, caret

## Methodology
___________________________________________
This study encompasses several steps including data cleaning, exploratory data analysis, model building, and interpretation of results.

## Data Cleaning
___________________________________________
Upon obtaining the data, initial steps were taken to ensure its quality and suitability for analysis. This included:

1.  Addressing missing values
2.  Rectifying any data entry errors
3.  Transforming variables as needed for analysis

# Insert your R code for Data Cleaning here

## Exploratory Data Analysis
___________________________________________
The cleaned data was then explored to identify any interesting patterns or relationships among the variables. This included:

1.  Generating descriptive statistics
2.  Undertaking correlation analysis
3.  Visualizing data via various graphs and plots

# Insert your R code for Exploratory Data Analysis here

## Model Building
___________________________________________
A linear regression model was developed to understand the relationship between air toxins and cancer incidences, taking into account the various demographic variables. The process involved:

1.  Splitting data into training and test sets
2.  Training the model using the training data
3.  Validating the model using the test data
4.  Evaluating the model's performance through metrics like Mean Squared Error (MSE), R-squared, and Adjusted R-squared

# Insert your R code for Model Building here

# Results
___________________________________________

The results, presented through various charts, plots, and tables, offer valuable insights into the relationship between air toxins, cancer incidence, and demographic vulnerability.

### Correlation Matrix

![Pearson_Corelation](Images/Pearson-R.png)


|            | tot_can   | MINORPCT  | LOWINCPCT | LESSHSPCT | LINGISOPCT | UNDER5PCT | OVER64PCT |
|------------|-----------|-----------|-----------|-----------|------------|-----------|-----------|
| tot_can    | 1.000000  | 0.2610215 | -0.143277 | -0.143161 | 0.181331   | 0.056534  | -0.370172 |
| MINORPCT   | 0.2610215 | 1.000000  | 0.379772  | 0.545848  | 0.596515   | 0.259567  | -0.437669 |
| LOWINCPCT  | -0.143277 | 0.379772  | 1.000000  | 0.522831  | 0.311371   | 0.169796  | -0.164524 |
| LESSHSPCT  | -0.143161 | 0.545848  | 0.522831  | 1.000000  | 0.469622   | 0.204986  | -0.145337 |
| LINGISOPCT | 0.181331  | 0.596515  | 0.311371  | 0.469622  | 1.000000   | 0.162958  | -0.233652 |
| UNDER5PCT  | 0.056534  | 0.259567  | 0.169796  | 0.204986  | 0.162958   | 1.000000  | -0.318561 |
| OVER64PCT  | -0.370172 | -0.437669 | -0.164524 | -0.145337 | -0.233652  | -0.318561 | 1.000000  |
---------------------------------------------------------------------------------------------------

### Cluster Means 

![KNN Plot](Images/KNN%20plot.png)

| Group | tot_can   | MINORPCT  | LOWINCPCT | LESSHSPCT | LINGISOPCT | UNDER5PCT | OVER64PCT |
|-------|-----------|-----------|-----------|-----------|------------|-----------|-----------|
| 1     | 0.221020  | 1.542698  | 1.049614  | 1.415888  | 1.307864   | 0.615692  | -0.679941 |
| 2     | -0.818329 | -0.561961 | 0.031986  | -0.097068 | -0.357277  | -0.269739 | 0.606600  |
| 3     | 0.875226  | -0.035656 | -0.518622 | -0.532300 | -0.172382  | 0.040011  | -0.412529 |
---------------------------------------------------------------------------------------------------

### Linear Regression 
Model MSE: 31.8514653229928

Coefficients and P-values:

|           | Estimate   | P-Value        |
|-----------|------------|----------------|
| Intercept | 32.658232  | 0.000000e+00   |
| MINORPCT  | 16.627000  | 7.783699e-33   |
| LOWINCPCT | -8.883775  | 2.380449e-19   |
| LESSHSPCT | -32.106470 | 1.738434e-43   |
| LINGISOPCT| 27.020164  | 5.008377e-12   |
| UNDER5PCT | -10.869478 | 1.443556e-02   |
| OVER64PCT | -25.858466 | 1.444787e-51   |
---------------------------------------------------------------------------------------------------


### Stepwise AIC Results

The model with the lowest AIC is the one without any removal of predictors.

Variable Importance (based on sum of squares): UNDER5PCT < LINGISOPCT < LOWINCPCT < MINORPCT < LESSHSPCT < OVER64PCT

### VIF Results

| Variable    | VIF       |
|-------------|-----------|
| MINORPCT    | 2.159948  |
| LOWINCPCT   | 1.408359  |
| LESSHSPCT   | 1.811304  |
| LINGISOPCT  | 1.628834  |
| UNDER5PCT   | 1.151737  |
| OVER64PCT   | 1.341494  |
---------------------------------------------------------------------------------------------------
 


![Bar_Plot](Images/Bar-R.png)

# Conclusion
___________________________________________
In conclusion, the study offers a detailed understanding of how air toxins contribute to cancer incidences and how these are influenced by various demographic factors. These findings can help formulate effective strategies to mitigate the risk of cancer in vulnerable communities, and inform policy decisions.

## References
___________________________________________
- [Environmental Justice (EJ) Screen dataset](https://www.epa.gov/ejscreen)
- [Oregon Department of Environmental Quality](https://www.oregon.gov/deq/pages/index.aspx)






