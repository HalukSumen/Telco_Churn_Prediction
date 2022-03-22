# Telco Customer Churn

## Exploratory Data Analysis + Data Visualization + Modelling 

### 1 - Abstract

In this project I made Exploratory Data Analysis, Data Visualisation and lastly Modelling. Dataset contains 7043 rows in csv file. Each example row represent a churned or not churned customoer with 21 different information(columns). Before modelling part I have to do Data Cleaning and I need to understand which features(columns) are more important for understand the customer behavior. Also I checked distribution of churned and not churned to make Undersampling or Oversampling but luckily dataset distribution is acceptable, but if a person will make Oversampling, accuracy it may be slightly higher. Later I made visualization of each columns to understand the dataset better and of course feature importance. In the modelling part, I used 9 different algorithms __CatBoost__ , __K-Neighbors__ , __XGBoost__ , __AdaBoost__ , __LightGBM__ , __Logistic Regression__ , __Gradient Boosting__ , __Random Forest__ , __D-Tree Classifier__ . Gradient Boosting algorithm gives the best accuracy with __0.804500__ which is slightly better CatBoost (__0.803600__) and AdaBoost (__0.803600__),also D-Tree Classifier gives the worst accuracy(__0.803600__). But my aim is Recall Score; because objective of this types of project is decreasing False Negatives(FN). In the end __Gradient Boosting__ (__0.541800__)recall score decent but with Oversampling or using scale_pos_weight in boosting algorithms can increase Recall Score.

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


Let's examine general structure of modelling part our example is Light-GBM.

First we are creating list for each items, because we want to keep them for comparing as a one list.
```
models =[]
accuracy= []
recall =[]
roc_auc= []
precision = []
f1 = []
```

In this part we are dropping gender and PhoneService and doing Label Encoding(encode target labels with value between 0 and n_classes-1) for Churn column.

```
df1 = df.drop(['gender','PhoneService'],axis=1).copy()
le = LabelEncoder()
df1['Churn']=le.fit_transform(df1['Churn'])
```

Then we are changing tenure data type int to float and for X we are dropping Churn column and for Y just giving Churn column.

```
df1['tenure']= df1['tenure'].astype(float)
df1= pd.get_dummies(df1)
X= df1.drop('Churn', axis=1)
y= df1['Churn']
```

Now we are using train test split and deciding test size and random state. we can add more parameters such as shuffle.

```
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
```

Here, we are calling our function also prediction our X_test data part.

```
lgbmc = LGBMClassifier()
lgbmc.fit(X_train, y_train)
y_pred = lgbmc.predict(X_test)
```

After our classifier works we need to see result, we are rounding results and showing 4 numbers after point(.).

```
accuracy.append(round(accuracy_score(y_test, y_pred),4))
recall.append(round(recall_score(y_test, y_pred),4))
roc_auc.append(round(roc_auc_score(y_test, y_pred),4))
precision.append(round(precision_score(y_test, y_pred),4))
f1.append(round(f1_score(y_test, y_pred),4))
```

Finally, we are adding our results to the list then print on the screen.

```
models = ['LightGBM']
result_df5 = pd.DataFrame({'Accuracy':accuracy,
                           'Recall':recall, 
                           'Roc_Auc':roc_auc, 
                           'Precision':precision, 
                           'F1 Score':f1}, 
                           index=models)
result_df5
```


Let's look output of our models.

* __CatBoost__ 

| Accuracy  | Recall    |  Roc_Auc  | Precision |  F1 Score |
| --------- | --------- | --------- | --------- | --------- |
| 0.8036	  | 0.5035	  | 0.7095	  | 0.6897	  | 0.5821    |  

* __K-Neighbors__ 

| Accuracy  | Recall    |  Roc_Auc  | Precision |  F1 Score |
| --------- | --------- | --------- | --------- | --------- |
| 0.7747	  | 0.4634	  | 0.6771	  | 0.6129	  | 0.5278    |


* __XGBoost__ 

| Accuracy  | Recall    |  Roc_Auc  | Precision |  F1 Score |
| --------- | --------- | --------- | --------- | --------- |
| 0.7875	  | 0.4861	  | 0.693	    | 0.6443    | 	0.5541  |


* __AdaBoost__ 

| Accuracy  | Recall    |  Roc_Auc  | Precision |  F1 Score |
| --------- | --------- | --------- | --------- | --------- |
| 0.8036	  | 0.5244	  | 0.7161	  |  0.6795 	| 0.5919    |


* __LightGBM__ 

| Accuracy  | Recall    |  Roc_Auc  | Precision |  F1 Score |
| --------- | --------- | --------- | --------- | --------- |
| 0.7993	  | 0.5261	  | 0.7137	  | 0.6652	  | 0.5875    |


* __Logistic Regression__ 

| Accuracy  | Recall    |  Roc_Auc  | Precision |  F1 Score |
| --------- | --------- | --------- | --------- | --------- |
| 0.7998	  | 0.5331	  | 0.7162	  |  0.6638   | 	0.5913  |


* __Gradient Boosting__ 

| Accuracy  | Recall    |  Roc_Auc  | Precision |  F1 Score |
| --------- | --------- | --------- | --------- | --------- |
| 0.8045    | 0.5418    |  0.7222	  | 0.6746    | 	0.601   |


* __Random Forest__ 

| Accuracy  | Recall    |  Roc_Auc  | Precision |  F1 Score |
| --------- | --------- | --------- | --------- | --------- |
| 0.7875    | 0.4774    |  0.6903   |  0.6478   | 0.5496    |


* __D-Tree Classifier__ 

| Accuracy  | Recall    |  Roc_Auc  | Precision |  F1 Score |
| --------- | --------- | --------- | --------- | --------- |
| 0.7307    | 0.5122    |  0.6622   |  0.5043   | 0.5082    |


### 5 - Result & Future Work

Totally we used 9 different algorithms __CatBoost__ , __K-Neighbors__ , __XGBoost__ , __AdaBoost__ , __LightGBM__ , __Logistic Regression__ , __Gradient Boosting__ , __Random Forest__ , __D-Tree Classifier__ . Gradient Boosting algorithm gives the best accuracy with (__0.804500__) which is slightly better than CatBoost (__0.803600__) and AdaBoost (__0.803600__),also D-Tree Classifier gives the worst accuracy(__0.803600__). But my aim is Recall Score; because objective of this types of project is decreasing False Negatives(FN). In the end __Gradient Boosting__ (__0.541800__)recall score decent but with Oversampling or using scale_pos_weight in boosting algorithms can increase Recall Score and gives better prediction about customer.
