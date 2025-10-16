# Date: 15-10-2025
# Name: VEDARANJAN S
# Register Number: 25016378
# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats
from sklearn.ensemble import IsolationForest  
df = pd.read_csv(r"C:\Users\acer\Downloads\Data_set (1).csv") 
display(df.head())
```
<img width="1720" height="547" alt="Screenshot 2025-10-16 081212" src="https://github.com/user-attachments/assets/4e1889d0-6bf6-4282-bda4-7d9f2feb1539" />
```
print(df.info())
```
<img width="640" height="516" alt="Screenshot 2025-10-16 081235" src="https://github.com/user-attachments/assets/4b38c92e-032a-473a-9620-91af626e6f98" /> 
```
display(df.describe(include='all').T) 
```
<img width="1503" height="541" alt="Screenshot 2025-10-16 081304" src="https://github.com/user-attachments/assets/22fe81e1-d7f2-4431-89ae-851a3fb77029" /> 
```
print("\nMissing values per column:")
print(df.isna().sum()) 
```
<img width="440" height="395" alt="Screenshot 2025-10-16 081326" src="https://github.com/user-attachments/assets/eef8fa73-450d-4a93-acdf-812655ac9eed" /> 
```
num_cols = df.select_dtypes(include=[np.number]).columns.tolist()
print("Numeric columns:", num_cols) 
```
<img width="1205" height="31" alt="Screenshot 2025-10-16 083408" src="https://github.com/user-attachments/assets/946884dd-41e2-4df5-8352-aa14b58fca31" />
```
for c in num_cols:
    plt.figure(figsize=(6,2))
    plt.title(f"Boxplot: {c}")
    plt.boxplot(df[c].dropna())
    plt.xlabel(c)
    plt.show() 
```
<img width="997" height="749" alt="Screenshot 2025-10-16 083643" src="https://github.com/user-attachments/assets/c945f084-87b0-427f-905f-adf9bae90fcc" /> 
<img width="919" height="751" alt="Screenshot 2025-10-16 083740" src="https://github.com/user-attachments/assets/0bef52af-eb74-4f74-90cd-df2c6edee580" /> 
<img width="1018" height="436" alt="Screenshot 2025-10-16 083829" src="https://github.com/user-attachments/assets/fa6fbfc2-5b67-4c0d-9c60-d61aacec1bba" /> 







# Result

Thus the data cleaning process on the given dataset is executed successfully.
