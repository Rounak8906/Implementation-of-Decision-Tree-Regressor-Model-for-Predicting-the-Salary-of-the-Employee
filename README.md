# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 1.Import pandas

2.Import Decision tree classifier

3.Fit the data in the model

4.Find the accuracy score


## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: ROUNAK SINGH
RegisterNumber:  212225240125
*/
```

```py
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
```

```py
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```

```py
x=data[["Position","Level"]]
x.head()
y=data["Salary"]
y.head()

```

```py
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)
```

```py
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred
from sklearn.metrics import r2_score
r2=r2_score(y_test,y_pred)
```
```
R2 score:  0.48611111111111116


```
```py
dt.predict([[5,6]])
```

## Output:
<img width="1041" height="322" alt="image" src="https://github.com/user-attachments/assets/1d650cba-e392-462b-9089-2f8b9f21526c" />
<img width="495" height="240" alt="image" src="https://github.com/user-attachments/assets/905c287a-1170-4044-90ff-35c77d79c2f0" />
<img width="863" height="157" alt="image" src="https://github.com/user-attachments/assets/1ea5b3f1-b827-4d07-97d0-41331d24dbdd" />
<img width="396" height="40" alt="image" src="https://github.com/user-attachments/assets/512e683d-7495-4c64-bffb-e7858418aa4c" />
<img width="236" height="35" alt="image" src="https://github.com/user-attachments/assets/1744d15f-3601-4a74-803d-31c9cbef5777" />


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
