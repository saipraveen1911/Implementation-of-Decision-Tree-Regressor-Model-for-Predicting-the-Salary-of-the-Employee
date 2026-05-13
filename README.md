# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Get the independent variable X and dependent variable Y.

2.Calculate the mean of the X -values and the mean of the Y -values.

3.Find the slope m of the line of best fit using the formula.

4.Compute the y -intercept of the line by using the formula.

5.Use the slope m and the y -intercept to form the equation of the line. 6. Obtain the straight line equation Y=mX+b and plot the scatterplot. 

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: SAI PRAVEEN C
RegisterNumber:212225230239
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.tree import DecisionTreeRegressor

# ------------------------------
# Step 1: Sample dataset
# ------------------------------
data = {
    'Position': ['Business Analyst', 'Junior Consultant', 'Senior Consultant',
                 'Manager', 'Country Manager', 'Region Manager',
                 'Partner', 'Senior Partner', 'C-level', 'CEO'],
    'Level': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Salary': [45000, 50000, 60000, 80000, 110000, 150000, 200000, 300000, 500000, 1000000]
}

df = pd.DataFrame(data)

# ------------------------------
# Step 2: Split features and target
# ------------------------------
X = df[['Level']]     # Feature (Level) as DataFrame
y = df['Salary']      # Target (Salary)

# ------------------------------
# Step 3: Create Decision Tree Regressor
# ------------------------------
regressor = DecisionTreeRegressor(random_state=42)
regressor.fit(X, y)

# ------------------------------
# Step 4: Predict salary
# ------------------------------
y_pred = regressor.predict(X)
print("Predicted salaries:", y_pred)

# FIX 1: Pass input as a DataFrame to avoid "Feature Name" warning
level_val = 6.5
level_df = pd.DataFrame([[level_val]], columns=['Level'])
predicted_salary = regressor.predict(level_df)

print(f"Predicted Salary for level {level_val}: {predicted_salary[0]}")

# ------------------------------
# Step 5: Visualize the results
# ------------------------------
# FIX 2: Use .item() or [0] to ensure scalars are passed to np.arange
X_min = X.values.min()
X_max = X.values.max()
X_grid = np.arange(X_min, X_max + 0.01, 0.01)
X_grid = X_grid.reshape(-1, 1)

# FIX 3: Convert X_grid back to DataFrame for prediction to stay consistent
X_grid_df = pd.DataFrame(X_grid, columns=['Level'])

plt.scatter(X, y, color='red', label='Actual Salary')
plt.plot(X_grid, regressor.predict(X_grid_df), color='blue', label='Decision Tree Prediction')
plt.title('Decision Tree Regression: Level vs Salary')
plt.xlabel('Level')
plt.ylabel('Salary')
plt.legend()
plt.show()  
*/
```

## Output:

<img width="1255" height="622" alt="ML EXP - 9" src="https://github.com/user-attachments/assets/1cc55df0-042d-4c49-ba55-be93ab13251e" />

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
