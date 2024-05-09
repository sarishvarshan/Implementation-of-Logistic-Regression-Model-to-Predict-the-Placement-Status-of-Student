# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the standard libraries.
2.Upload the dataset and check for any null or duplicated values using .isnull() and .duplicated() function respectively.
3.LabelEncoder and encode the dataset.
4.Import LogisticRegression from sklearn and apply the model on the dataset.
5.Predict the values of array.
6.Calculate the accuracy, confusion and classification report by importing the required modules from sklearn.
7.Apply new unknown values

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: Sarish Varshan V
RegisterNumber: 212223230196 
*/
```

## Output:
```
import pandas as pd
data=pd.read_csv("C:/Users/giri9/OneDrive/Documents/Desktop/Placement_Data4.csv")
data.head()
```
![Screenshot 2024-03-22 085137](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/8384c8f7-bad2-4ff4-a4b6-42cc0e055cc8)
```
data1=data.copy()
data1=data1.drop(["sl_no","salary"],axis=1)
data1.head()
```
![Screenshot 2024-03-22 085542](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/6606719f-a17a-4629-a89d-bb40b0238b2e)
```
data1.isnull()
```
![Screenshot 2024-03-22 085722](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/10657ed8-a790-4cc8-b878-d47cc54da2ca)
```
data.duplicated().sum()
```
![Screenshot 2024-03-22 085851](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/112da9aa-02b7-4b81-a13b-2450abfe3f16)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data1["gender"]=le.fit_transform(data1["gender"])
data1["ssc_b"]=le.fit_transform(data1["ssc_b"])
data1["hsc_b"]=le.fit_transform(data1["hsc_b"])
data1["hsc_s"]=le.fit_transform(data1["hsc_s"])
data1["degree_t"]=le.fit_transform(data1["degree_t"])
data1["workex"]=le.fit_transform(data1["workex"])
data1["specialisation"]=le.fit_transform(data1["specialisation"])
data1["status"]=le.fit_transform(data1["status"])
data1
```
![Screenshot 2024-03-22 090027](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/ca9c7499-7901-43d3-bc8c-0e50152acc68)
```
x=data1.iloc[:,:-1]
x
```
![Screenshot 2024-03-22 090120](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/d0526e56-b970-401d-843b-01415a5ad81b)
```
y=data1["status"]
y
```
![Screenshot 2024-03-22 090223](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/609939e5-e034-499d-98e9-1402fa3c4c38)
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2, random_state=0)
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.linear_model import LogisticRegression
lr=LogisticRegression(solver="liblinear")
lr.fit(x_train,y_train)
y_pred=lr.predict(x_test)
y_pred
```
![Screenshot 2024-03-22 090313](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/53c4787a-a273-47ba-9e7a-36d3da0d30f4)
```
from sklearn.metrics import accuracy_score
accuracy=accuracy_score(y_test,y_pred)
accuracy
```
![Screenshot 2024-03-22 090359](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/5d681e66-8b59-4372-ba1f-c53532f43af8)
```
from sklearn.metrics import  classification_report
classification_report1=classification_report(y_test,y_pred)
print(classification_report1)
```
![Screenshot 2024-03-22 090449](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/9effff67-797a-4395-91d8-5a8215327910)
```
lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])
```

![Screenshot 2024-03-22 090605](https://github.com/sarishvarshan/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/152167665/1719311c-4515-48da-a4af-59d072ec1035)



## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
