# Air-Toxin-Cancer-vs-Demographics-Analysis
A detailed analysis on the dataset related to air toxics and cancer risk. 
![KNN Plot](Images/KNN%20plot.png)

### Correlation Matrix

|            | tot_can   | MINORPCT  | LOWINCPCT | LESSHSPCT | LINGISOPCT | UNDER5PCT | OVER64PCT |
|------------|-----------|-----------|-----------|-----------|------------|-----------|-----------|
| tot_can    | 1.000000  | 0.2610215 | -0.143277 | -0.143161 | 0.181331   | 0.056534  | -0.370172 |
| MINORPCT   | 0.2610215 | 1.000000  | 0.379772  | 0.545848  | 0.596515   | 0.259567  | -0.437669 |
| LOWINCPCT  | -0.143277 | 0.379772  | 1.000000  | 0.522831  | 0.311371   | 0.169796  | -0.164524 |
| LESSHSPCT  | -0.143161 | 0.545848  | 0.522831  | 1.000000  | 0.469622   | 0.204986  | -0.145337 |
| LINGISOPCT | 0.181331  | 0.596515  | 0.311371  | 0.469622  | 1.000000   | 0.162958  | -0.233652 |
| UNDER5PCT  | 0.056534  | 0.259567  | 0.169796  | 0.204986  | 0.162958   | 1.000000  | -0.318561 |
| OVER64PCT  | -0.370172 | -0.437669 | -0.164524 | -0.145337 | -0.233652  | -0.318561 | 1.000000  |

![Pearson_Corelation](Images/Pearson-R.png)

### Cluster Means 

| Group | tot_can   | MINORPCT  | LOWINCPCT | LESSHSPCT | LINGISOPCT | UNDER5PCT | OVER64PCT |
|-------|-----------|-----------|-----------|-----------|------------|-----------|-----------|
| 1     | 0.221020  | 1.542698  | 1.049614  | 1.415888  | 1.307864   | 0.615692  | -0.679941 |
| 2     | -0.818329 | -0.561961 | 0.031986  | -0.097068 | -0.357277  | -0.269739 | 0.606600  |
| 3     | 0.875226  | -0.035656 | -0.518622 | -0.532300 | -0.172382  | 0.040011  | -0.412529 |

![KNN Plot](Images/KNN%20plot.png)

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


### Stepwise AIC Results

The model with the lowest AIC is the one without any removal of predictors.

Variable Importance (based on sum of squares): UNDER5PCT < LINGISOPCT < LOWINCPCT < MINORPCT < LESSHSPCT < OVER64PCT

### VIF Results

| MINORPCT     |           |  
| LOWINPCT     | -0.818329 | 
| LESSHSPCT    | 0.875226  | 
| LINGISPCT    | -0.818329 | 
| UNDER5PCT    | 0.875226  | 
| OVER64PCT    | 0.875226  | 


![Bar_Plot](Images/Bar-R.png)

