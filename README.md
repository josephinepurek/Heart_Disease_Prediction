# Heart_Disease_Prediction
To build model that can predict the heart disease existence based on known attributes from a patient. 

## ABOUT
Each year, 32% of all deaths around the world caused by Cardiovascular Diseases (CVDs). Cardiovascular diseases (CVDs) are a group of disorders of the heart and blood vessels. On average, 85% of the number were caused by heart attack and stroke. In this project, the prediction machine of heart diseases (CVDs) existence on a person will be built based 13 existence feature relate to human cardiovascular system.


## DATA DESCRIPTION
Dataset used for this project is consist of 13 features and 1 target variables.

Feature:
1. `age` - age (in years) of each respondent (corresponding one on one with the row) | continuous variable
2. `sex` - gender of each respondent (1 = male ; 0 = female) | categorical variable
3. `cp` - chest pain type (4 values) | ordinal categorical variable :  
Value 0 "typical angina"  
Value 1 "atypical angina"  
Value 2 "non-anginal pain"  
Value 3 "asymptomatic"
4. `trestbps` - resting blood pressure (in mm Hg on admission to the hospital) | continuous variable
5. `chol` - serum cholestoral in mg/dl | continuous variable
6. `fbs` - fasting blood sugar > 120 mg/dl (1 = true; 0 = false) | categorical variable
7. `restecg` - resting electrocardiographic results (values 0,1,2) | ordinal categorical variable :   
Value 0 "normal"  
Value 1 "having ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV)"  
Value 2 "showing probable or definite left ventricular hypertrophy by Estes' criteria" 
8. `thalach` - maximum heart rate achieved | continuous variable
9. `exang` - exercise induced angina (1 = yes; 0 = no) | categorical variable
10. `oldpeak` - ST depression induced by exercise relative to rest | continuous variable
11. `slope` - the slope of the peak exercise ST segment | ordinal categorical variable :  
Value 0 "upsloping"  
Value 1 "flat"  
Value 2 "downsloping"
12. `ca` - number of major vessels (0-4) colored by flourosopy | ordinal categorical variable 
13. `thal`: 0 = normal; 1 = fixed defect; 2 = reversable defect | ordinal categorical variable

Target: 
`target` - Valued as follows: 0 = no heart disease ; 1 = heart disease.


## DATA CLEANING
Duplicate row in this dataset can be categorized as huge, which valued 71% row of the dataset.
There are 5 rows in dataset categorized as outliers based on analysis using feature `oldpeak` as basis for data grouping. This outliers will be dropped from final dataframe.


## EXPLORATORY DATA ANALYSIS

### Target Data Distribution
Target data in dataset are balancedly distributed for both of the value 0 and 1.

### Correlation
![image](https://user-images.githubusercontent.com/88548913/138568292-ab68a95d-86ab-49b2-b5ff-58e2dc8dd313.png)  
Based on the generated plot, we will use >0.4 as threshold for strong correlation, then we can conclude that:  
1. Features `cp`, `thalach`, `exang`, `oldpeak`, and `ca` have strong correlation with the target variable (heart disease existence in patient)
2. There is multicollinearity between feature `thalach` & `age` and features `slope` and `oldpeak`.


## MACHINE LEARNING MODEL
Step to build model:
1. Split dataset into 2; train and test dataset,
2. Fit the model to our dataset ; using train dataset,
3. Predict heart disease using test dataset,
4. Measure model accuracy.

Model built in this project with accuracy score:
1. Logistic Regression (using standardized data) : 86.67%
2. Gaussian Naive-Bayes : 85%
3. SVC (Support Vector Classifier) : 66.67%
4. Random Forest : 66.67%
5. Decision Tree : 78.33%


## CONCLUSION
The selected model is Logistic Regression (using standardized data) with accuracy score 86.67%.
