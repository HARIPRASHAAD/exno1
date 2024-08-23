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
 ### READING THE GIVEN DATA
 ```
import pandas as pd
import numpy as np
df = pd.read_csv('SAMPLEIDS.csv')
df
```
![read](https://github.com/user-attachments/assets/d049f907-cfd0-4335-b3b9-464439e4b833)

### GETTING INFORMATION OF THE DATA 

```
df.describe()
```
![describe](https://github.com/user-attachments/assets/beb5f686-11bc-4794-aa7b-6ef9b1e1c992)4

```
df.info()
```

![info](https://github.com/user-attachments/assets/da2a5f9f-0988-487f-81ce-93eef92e81b0)
```
df.heaad()
```
![head](https://github.com/user-attachments/assets/de102b53-0ca9-493f-b811-91bc7e8f97b4)
```
df.tail()
```
![tail](https://github.com/user-attachments/assets/858ba30e-756d-4ed4-a398-34c35abf79f9)

```
df.shape
```
```
(21, 12)
```
### REMOVING NULL VALUES FORM THE DATA 
```
df.isnull()
```
![is null](https://github.com/user-attachments/assets/74553a9d-0c97-4a14-9de3-ecaac3960caf)

```
df.isnull().sum()
```
![is null sum](https://github.com/user-attachments/assets/50e322b2-1d19-4f6a-8083-2a4940b271a2)

```
df.isnull().any()
```
![is null any](https://github.com/user-attachments/assets/fd184f80-613a-4c51-9528-e6d9e9c4c3d7)

```
df.dropna(axis=0)
```
![dropna](https://github.com/user-attachments/assets/afbad0f5-244d-4033-be98-e2f14faa6d5b)

### SAVING THE CLEAN DATA 
```
df = df.dropna(axis=0)
df
```
![dropna](https://github.com/user-attachments/assets/23b194fe-fc59-4156-884e-3f59757d8445)

###r REMOVING OUTLIERS USING IQR 
```
import seaborn as sns
pf=pd.read_csv('heights.csv')
pf
```
![Screenshot (165)](https://github.com/user-attachments/assets/465cf710-a8bb-4f75-913d-9cfbd685250e)

```
sns.boxplot(data=pf)
```
![image](https://github.com/user-attachments/assets/ae069561-4b2e-4cee-9769-83b6f2174c89)
```
sns.scatterplot(data=pf)

```
![image](https://github.com/user-attachments/assets/1170d545-0a22-4bfc-ba03-d8c12d0b043f)
```

Q1 = pf['height'].quantile(0.25)
Q3 = pf['height'].quantile(0.75)
IQR = Q3 - Q1
LB = Q1 - 1.5 * IQR
UB = Q3 + 1.5 * IQR

outliers = pf[(pf['height'] < LB) | (pf['height'] > UB)]

print("Lower Bound:", LB)
print("Upper Bound:", UB)
print("Outliers:\n", outliers)
```
![image](https://github.com/user-attachments/assets/29036b0e-3e88-4a52-9e7c-f3d4d5f38da3)








# Result
          <<include your Result here>>
