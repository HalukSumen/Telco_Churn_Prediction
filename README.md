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
  <img width="700" height="400" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/ChurnAndNot.png">
</p>

* Customer did churn: 26.54  %  --> (1869 customer)
* Customer did not churn: 73.46  %  --> (5174 customer)

Secondly I visualized all columns according to numerical and categorical types. 
As you can see in the images below, there are four columns as numerical and rest of the columns are categorical.

<p align="center">
  <img width="700" height="400" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/tenure.png">
</p>
<p align="center">
  <img width="700" height="400" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/MonthlyCharges.png">
</p>
<p align="center">
  <img width="700" height="400" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/TotalCharges.png">
</p>
<p align="center">
  <img width="700" height="400" src="https://github.com/HalukSumen/Telco_Churn_Prediction/blob/main/images/SeniorCitizen.png">
</p>
### 4 - Modelling 

### 5 - Result & Future Work
