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
df=pd.read_csv('SAMPLEIDS.csv')
df
```
<img width="1006" height="743" alt="image" src="https://github.com/user-attachments/assets/4f3729bc-9395-423f-af42-ae2bc8e05082" />

```
df.head()
```

<img width="860" height="189" alt="image" src="https://github.com/user-attachments/assets/fff8b6a9-07c0-42be-b36e-ca6e1e7213be" />

```
df.tail()
```

<img width="888" height="192" alt="image" src="https://github.com/user-attachments/assets/68225ea1-5818-448d-bad7-429c14ae2a91" />

```
df.isnull()
```

<img width="777" height="706" alt="image" src="https://github.com/user-attachments/assets/57ee48a3-1bd9-4c94-ab3d-e69e2c9cba51" />

```
df.notnull()
```

<img width="769" height="706" alt="image" src="https://github.com/user-attachments/assets/0db37aea-1dd6-40dc-9e58-2244a61e6671" />

```
df.isnull().sum()
```

<img width="131" height="278" alt="image" src="https://github.com/user-attachments/assets/7282a3e5-b6e2-4d16-815e-27194d6ef34e" />

```
df.dropna(axis=0)
```

<img width="922" height="451" alt="image" src="https://github.com/user-attachments/assets/7ffc1566-4a3d-4525-9a93-60986142394e" />

```
df.dropna(axis=0)
```

<img width="896" height="449" alt="image" src="https://github.com/user-attachments/assets/9458e914-a737-4bcf-bfe0-af208c87c05a" />

```
df.dropna(axis=1)
```

<img width="273" height="711" alt="image" src="https://github.com/user-attachments/assets/0fc1cdb1-6847-4d0d-86ca-0c9efafcb700" />

```
df.fillna(_)
```

<img width="923" height="708" alt="image" src="https://github.com/user-attachments/assets/8a9867b5-1151-465b-bd3d-ed205d61966e" />

```
df.fillna(method='ffill')
```

<img width="904" height="707" alt="image" src="https://github.com/user-attachments/assets/68a8db09-2465-4bc7-a263-029f9d7471fd" />

```
df.fillna(method='bfill')
```

<img width="909" height="702" alt="image" src="https://github.com/user-attachments/assets/dd30a5e6-ed52-48e5-afaa-c6541efad4a1" />

```
df.fillna({'GENDER':'MALE','NAME':'SANTHOSH','ADDRESS':'KANCHIPURAM','M1':'76.0','M2':'69.0','M3':'80.0','M4':'76.0','TOTAL':'301.0','AVG':'100.333333'})
```

<img width="920" height="699" alt="image" src="https://github.com/user-attachments/assets/103c2c81-e3a8-4a66-8fab-19d2b369bd24" />

```
import pandas as pd
ir=pd.read_csv("iris.csv")
ir
```

<img width="559" height="430" alt="image" src="https://github.com/user-attachments/assets/c83b4180-39dd-474d-844e-87116d757537" />

```
ir.describe()
```

<img width="488" height="297" alt="image" src="https://github.com/user-attachments/assets/39d88ca5-3c33-4fdb-bbec-a50e62abf788" />

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```

<img width="651" height="541" alt="image" src="https://github.com/user-attachments/assets/57e3e51e-646c-4a68-8f25-1e081b268e0c" />

```
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
IQR=Q3-Q1
print(IQR)
```

<img width="56" height="34" alt="image" src="https://github.com/user-attachments/assets/d97e8c6c-3217-4bab-9062-611bf5b30dbe" />

```
rid=ir[(ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR))]
rid['sepal_width']
```

<img width="340" height="109" alt="image" src="https://github.com/user-attachments/assets/1b4f4b86-0f17-4ac8-af88-d055a373f4ff" />

```
delid=ir[~((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
delid
```

<img width="605" height="432" alt="image" src="https://github.com/user-attachments/assets/b216982f-8a9f-4682-8945-e3311899aec2" />

```
sns.boxplot(x='sepal_width',data=delid)
```

<img width="729" height="572" alt="image" src="https://github.com/user-attachments/assets/b388cf23-721a-4d5d-8aed-140b565f72ec" />

```
import numpy as np
import scipy.stats as stats
xyz=np.abs(stats.zscore(ir['sepal_width']))
xyz
```

<img width="473" height="253" alt="image" src="https://github.com/user-attachments/assets/4b174e9a-5443-4c33-a56b-b8e9bd084e0e" />

```
ir1=ir[xyz>3]
ir1
```
<img width="672" height="100" alt="image" src="https://github.com/user-attachments/assets/c84aa576-d572-4e40-97c3-91a36ec9adfb" />

# Result

Thus the data cleaning process on the given dataset is executed successfully.
