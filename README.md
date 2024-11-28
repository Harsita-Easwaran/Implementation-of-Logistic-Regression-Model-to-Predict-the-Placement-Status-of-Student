# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: Harsita Easwaran
RegisterNumber:  24013629
*/
```
import pandas as pd
data=pd.read_csv(r"Placement_Data.csv")
data.head
data1=data.copy()
data1=data1.drop(["sl_no","salary"],axis=1)
data1.head()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data1["gender"] = le.fit_transform(data1["gender"])
data1["ssc_b"] = le.fit_transform(data1["ssc_b"])
data1["hsc_b"] = le.fit_transform(data1["hsc_b"])
data1["hsc_s"] = le.fit_transform(data1["hsc_s"])
data1["degree_t"] = le.fit_transform(data1["degree_t"])
data1["workex"] = le.fit_transform(data1["workex"])
data1["specialisation"] = le.fit_transform(data1["specialisation"])
data1["status"] = le.fit_transform(data1["status"])
data1
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression 
x= data1.drop("status", axis=1)
y=data1["status"]
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
lr=LogisticRegression(solver="liblinear")
lr.fit(x_train,y_train)
y_pred=lr.predict(x_test)
y_pred
from sklearn.metrics import accuracy_score 
accuracy=accuracy_score(y_test,y_pred)
accuracy
from sklearn.metrics import confusion_matrix 
confusion=confusion_matrixy_test,y_pred)
confusion
from sklearn.metrics import classification_report 
classification report1=classification_report (y_test,y_pred)
print(classification_report1)
Ir.predict ([[1,80,1,90,1,1,90,1,0,85,1,85]])
## Output:
![the Logistic Regression Model to Predict the Placement Status of Student](sam.png)
![Screenshot 2024-11-29 003353](https://github.com/user-attachments/assets/8de27ab0-ea6c-433c-8473-d352255d55b6)
![Screenshot 2024-11-29 003401](https://github.com/user-attachments/assets/28bac612-285c-488b-b577-b5d3ca3e95ba)
![Screenshot 2024-11-29 003408](https://github.com/user-attachments/assets/1db7d2a5-ddfa-4764-832c-d3c5dc4336db)
![Screenshot 2024-11-29 003416](https://github.com/user-attachments/assets/f750b43d-777d-42c5-803f-e13d8237cb0d)
![Screenshot 2024-11-29 003422](https://github.com/user-attachments/assets/93361981-9587-4f5f-8aba-1390dd067ca4)
![Screenshot 2024-11-29 003427](https://github.com/user-attachments/assets/a01b9462-c565-4c4b-b1a1-a611d48ba418)
![Screenshot 2024-11-29 003433](https://github.com/user-attachments/assets/ebb11b79-9acd-4f23-a4b2-c0a046d759a7)


## Result:

Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
