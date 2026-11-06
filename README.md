# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required packages and print the present data.
2. Print the placement data and salary data.
3. Find the null and duplicate values.
4. Using logistic regression find the predicted values of accuracy , confusion matrices.
5. Display the results.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: Harsita Easwaran
RegisterNumber:  212224220036
*/
```
```
import pandas as pd

data = pd.read_csv("Placement_Data.csv")
print(data.head())

data1 = data.copy()
data1 = data1.drop(["sl_no", "salary"], axis=1)

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

data1["gender"] = le.fit_transform(data1["gender"])
data1["ssc_b"] = le.fit_transform(data1["ssc_b"])
data1["hsc_b"] = le.fit_transform(data1["hsc_b"])
data1["hsc_s"] = le.fit_transform(data1["hsc_s"])
data1["degree_t"] = le.fit_transform(data1["degree_t"])
data1["workex"] = le.fit_transform(data1["workex"])
data1["specialisation"] = le.fit_transform(data1["specialisation"])
data1["status"] = le.fit_transform(data1["status"])

print(data1)

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression

x = data1.drop("status", axis=1)
y = data1["status"]

x_train, x_test, y_train, y_test = train_test_split(
    x, y, test_size=0.2, random_state=0
)

lr = LogisticRegression(solver="liblinear")
lr.fit(x_train, y_train)

y_pred = lr.predict(x_test)
print(y_pred)

from sklearn.metrics import accuracy_score

accuracy = accuracy_score(y_test, y_pred)
print("Accuracy =", accuracy)

from sklearn.metrics import confusion_matrix

confusion = confusion_matrix(y_test, y_pred)
print("Confusion Matrix:")
print(confusion)

from sklearn.metrics import classification_report

classification_report1 = classification_report(y_test, y_pred)
print(classification_report1)

# Predict placement for new student
new_student = pd.DataFrame(
    [[1, 80, 1, 90, 1, 1, 90, 1, 0, 85, 1, 85]],
    columns=x.columns
)

prediction = lr.predict(new_student)
print("Placement Prediction =", prediction)
```

## Output:
<img width="1214" height="910" alt="image" src="https://github.com/user-attachments/assets/89ee48c8-ea3f-43b1-a4e1-096a6d2b6929" />
<img width="1200" height="1074" alt="image" src="https://github.com/user-attachments/assets/bf7977df-e60c-4b48-8665-97660321fd85" />



## Result:

Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
