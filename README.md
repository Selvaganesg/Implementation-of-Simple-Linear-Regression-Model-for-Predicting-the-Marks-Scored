# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.  Imports
2) Load dataset
3) Prepare input X and target Y
4) Train/test split
5) Create and train the linear model
6) Predict on test set
7) Plots
8) Evaluation metrics
9) Predict new samples
10) 
## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: Selvaganesh B
RegisterNumber:212224230258
*/
```
```
import pandas as pd
import numpy as np 
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error, mean_squared_error
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
df = pd.read_csv('/content/exp_2_dataset_student_scores.csv')   # CSV should have two columns, e.g. "Hours","Scores"
print("First 5 rows:\n", df.head(), "\n")
print("Last 5 rows:\n", df.tail(), "\n")

X = df.iloc[:, :-1].values   # all rows, all columns except last -> shape (n_samples, 1)
Y = df.iloc[:, -1].values    # all rows, last column -> shape (n_samples,)
print("X (features):", X.flatten())
print("Y (targets):", Y)

X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size=1/3, random_state=0)
print("\nTraining samples:", len(X_train), " Testing samples:", len(X_test))

Y_pred = regressor.predict(X_test)
print("\nPredicted values:", np.round(Y_pred, 2))
print("Actual values   :", Y_test)

plt.figure(figsize=(6,4))
plt.scatter(X_train, Y_train, color="orange", label="Training data")
plt.plot(X_train, regressor.predict(X_train), color="red", label="Fitted line")
plt.title("Hours vs Scores (Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.legend()
plt.grid(True)
plt.show()

order = np.argsort(X_test.flatten())
X_test_sorted = X_test.flatten()[order]
Y_test_sorted = Y_test[order]
Y_pred_sorted = Y_pred[order]
plt.figure(figsize=(6,4))
plt.scatter(X_test, Y_test, color="blue", label="Test data")
plt.plot(X_test_sorted, Y_pred_sorted, color="green", label="Predictions")
plt.title("Hours vs Scores (Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.legend()
plt.grid(True)
plt.show()

```
## Output:
<img width="308" height="288" alt="image" src="https://github.com/user-attachments/assets/496875ea-c95f-4ae2-ad11-0eef8f718780" />
<img width="752" height="83" alt="image" src="https://github.com/user-attachments/assets/6396d139-8812-4be0-82e7-f0ebb4d959b9" />
<img width="311" height="72" alt="image" src="https://github.com/user-attachments/assets/3c3b4c99-f874-4335-893f-f17dd375c820" />
<img width="665" height="62" alt="image" src="https://github.com/user-attachments/assets/71b1a3f2-2e5f-4ccf-9d60-6b3b13691447" />
<img width="530" height="400" alt="image" src="https://github.com/user-attachments/assets/debd3490-cb2f-49fe-847e-aeeaf39c7e8e" />
<img width="536" height="397" alt="image" src="https://github.com/user-attachments/assets/6e0d705b-107e-4a50-a9dc-37a026f9154d" />



## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
