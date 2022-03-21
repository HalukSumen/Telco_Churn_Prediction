# Telco Customer Churn ----- REPORT WORK IN PROGRESS

## Exploratory Data Analysis + Data Visualization + Modelling 

### 1 - Abstract


### 2 - Data
<a href="https://www.kaggle.com/blastchar/telco-customer-churn">Dataset</a> contains 21 columns and 7043 rows.

Columns Description:
* __CustomerID__ = A unique ID that identifies each customer.
* __Gender__ = The customer’s gender.
* __Senior Citizen__ = Indicates if the customer is 65 or older.
* __Partner__ = Indicates if the customer is married.
* __Dependents__ = Indicates if the customer lives with any dependents.
* __Tenure__ = Indicates the total amount of months that the customer has been with the company.
* __Phone Service__ = Indicates if the customer subscribes to home phone service with the company
* __Multiple Lines__ = Indicates if the customer subscribes to multiple telephone lines with the company.
* __Internet Service__ = Indicates if the customer subscribes to Internet service with the company.
* __Online Security__ = Indicates if the customer subscribes to an additional online security service provided by the company.
* __Device Protection__ = Indicates if the customer subscribes to an additional device protection plan for their Internet equipment provided by the company.
* __Tech Support__ = Indicates if the customer subscribes to an additional technical support plan from the company with reduced wait times.
* __Streaming TV__ = Indicates if the customer uses their Internet service to stream television programing from a third party provider.
* __Streaming Movies__ = Indicates if the customer uses their Internet service to stream movies from a third party provider.
* __Contract__ = Indicates the customer’s current contract type: Month-to-Month, One Year, Two Year.
* __Paperless Billing__ = Indicates if the customer has chosen paperless billing.
* __Payment Method__ = Indicates how the customer pays their bill.
* __Monthly Charges__ = Indicates the customer’s current total monthly charge for all their services from the company.
* __Total Charges__ = Indicates the customer’s total charges, calculated to the end of the quarter specified above.
* __Churn__ = Yes = the customer left the company this quarter. No = the customer remained with the company. Directly related to Churn Value.

### 3 - Exploratory Data Analysis

Firstly, I would like to see distribution of the data, because we may need to use Undersampling or Oversampling. As in the image below, dataset is fairly acceptable.

<p align="center">
  <img width="892" height="352" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/ChurnAndNot.png">
</p>

* Customer did churn: __26.54__  %  --> (1869 customer)
* Customer did not churn: __73.46__  %  --> (5174 customer)

Secondly, I visualized all columns according to numerical and categorical types. 
As you can see in the images below, there are four columns as numerical and rest of the columns are categorical.

In these plots we are observing, 
New clients most likely to churn
Clients with higher monthly charges more likely to churn
Clients with less total charges more likely to churn
Senior citizen less likely to churn
Tenure and MontlyCharges are important features for churn
<p align="center">
  <img width="622" height="333" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/tenure.png">
</p>

<p align="center">
  <img width="622" height="333" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/MonthlyCharges.png">
</p>

<p align="center">
  <img width="622" height="333" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/TotalCharges.png">
</p>

<p align="center">
  <img width="622" height="333" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/SeniorCitizen.png">
</p>

In those images we are observing, gender is not important for churn.
<p align="center">
  <img width="621" height="568" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/1.png">
</p>

<p align="center">
  <img width="621" height="568" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/2.png">
</p>


After these steps I want to see, Pearson correlation and Spearmen correlation. I used both because, Pearson evaluates linear relationship of columns, and Spearmen evaluates Monotonic relationship of columns.

__Important! :__  In a monotonic relationship, variables are likely to move in same direction but not necessarily at stable rate, but in Linear relationship, variables are move in same direction and stable rate.

__Pearson Correlation__
<p align="center">
  <img width="793" height="579" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/Pearson.png">
</p>

__Spearman Correlation__
<p align="center">
  <img width="793" height="579" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/Spearman.png">
</p>


Lastly, we are seeing Feature importance according to churn, result is not suprising. Top 3 important features are 'Tenure', 'Monthly Contract', and 'Total Charges'.
<p align="center">
  <img width="794" height="699" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/Feature%20Importance.png">
</p>

### 4 - Modelling 

In this part we are choosing which algorithms we will use and compare algorithms according to classification report. In this report Accuracy, Recall, Precision and F1 Score exist. For us Accuracy most important feature.
Let's see each of for understand better.

* __Accuracy:__ A Measure of a how good of the model.

* __Recall:__ Fraction of relevant instances that were retrieved.

* __Precision:__ Fraction of relevant instances among the retrieved instances.

* __F1:__ A measure of a test's accuracy.

<a href="https://www.researchgate.net/figure/Calculation-of-Precision-Recall-and-Accuracy-in-the-confusion-matrix_fig3_336402347"><img src="https://www.researchgate.net/publication/336402347/figure/fig3/AS:812472659349505@1570719985505/Calculation-of-Precision-Recall-and-Accuracy-in-the-confusion-matrix.ppm" alt="Calculation of Precision, Recall and Accuracy in the confusion matrix."/></a>

Let's look our models one by one and output of each of them.

* __CatBoost__ 

* __K-Neighbors__ 

* __XGBoost__ 

* __AdaBoost__ 

* __LightGBM__ 

* __Logistic Regression__ 

* __Gradient Boosting__ 

* __Random Forest__ 

* __D-Tree Classifier__ 







### 5 - Result & Future Work

