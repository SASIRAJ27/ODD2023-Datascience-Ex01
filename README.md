# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE 
## DATA_SET.CSV FILE
  ```
import pandas as pd
import numpy as np
df = pd.read_csv("/content/Data_set.csv")
df.head(5)
df.info()
df.isnull().sum()
#MODE:
df['show_name'] = df['show_name'].fillna(df['show_name']).mode()[0]
df['aired_on'] = df['aired_on'].fillna(df['aired_on']).mode()[0]
df['original_network'] = df['original_network'].fillna(df['original_network']).mode()[0]
#MEAN:
df['rating'] = df['rating'].fillna(df['rating']).mean()
df['current_overall_rank'] = df['current_overall_rank'].fillna(df['current_overall_rank']).mean()
#FORWARD METHOD:
df['watchers'] = df['watchers'].fillna(method='ffill')
#DUPLICATES:
df.duplicated()
df.info()
df.isnull().sum()
```
## LOAN_DATA.CSV
```
import pandas as pd
import numpy as np
df = pd.read_csv("/content/Loan_data.csv")
df.head()
df.info()
df.isnull().sum()
#MODE:
df['Gender'] = df['Gender'].fillna(df['Gender'].mode()[0])
df['Self_Employed'] = df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])
df['Dependents'] = df['Dependents'].fillna(df['Dependents'].mode()[0])
#MEAN:
df['LoanAmount'] = df['LoanAmount'].fillna(df['LoanAmount'].median())
#VALUE METHOD:
df['Loan_Amount_Term'] = df['Loan_Amount_Term'].fillna(value=360.0)
#BACKWARD METHOD:
df['Credit_History'] = df['Credit_History'].fillna(method='bfill')
#DUPLICATES:
df.duplicateed()
df.info()
df.isnull().sum()
```
# OUTPUT:
### First File
## Data_Set.csv FILE
![241768381-83d08586-cbfa-48d0-90b5-de060ff36cdd](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/096ebf50-820b-4821-a648-4c2fc543f326)
## INFO BEFORE CLEANING
![241768446-a39cd744-ed52-4c54-b33e-66aa5f176b1e](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/8bc95b43-8525-469d-a60d-0a0b805b1ff4)
## Isnull.().sum() before cleaning
![241769110-3e77f930-b20f-4612-8d68-0f6bb8b4f8a9](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/c1badb83-3dc8-444d-b240-688e252d71ee)
## MODE
![241769135-dc39e114-7014-4134-ba00-0e1fdc885b65](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/09da54f8-3035-49ff-905a-7bf25de75a22)
## MEAN
![241769156-0c8676ae-081c-4566-b04f-5fbced11645d](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/08ec8db5-61f7-4a4a-8db2-6daff478b99f)
## FORWARD METHOD
![241769361-b21e0779-c4fe-4be5-88ea-a99aa18e7dc0](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/e876851f-b725-4a88-9614-b4de20ce6118)
## DUPLICATES
![241769400-1e75e999-7c30-436e-a384-b2a62a4fbaba](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/60030d79-1b20-4adf-a419-bb8c00d500f5)
## INFO AFTER CLEANING
![241769468-6f65eee3-5021-4e40-94f3-bb6b08afb3cd](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/1fccbf0e-ab6d-4abc-9380-4b690c340771)
## isnull().sum() after cleaning
![241769567-4a090f7c-3df2-4c35-ab72-3a01b2b03ca1](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/7ca68f50-9535-44ac-a77a-69dfd762c8cf)

### Second File
## Loan_Data.csv FILE
![241769645-2798f1e4-02fb-45b1-9563-571b1ebbbc0d](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/8c714273-f1e3-4a35-982d-8abfe4503b62)
## INFO BEFORE CLEANING
![241769724-d3140955-abff-49b2-bf71-78014c6f9aca](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/0476d080-f14d-4540-b064-c4d6bdd9de4b)
## Isnull.().sum() before cleaning
![241769888-a5757c95-4a1d-4986-a912-fe0f8f948a9d](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/7d9cc56f-ffd3-4a0e-9a01-96fdaf44333a)
## MODE
![241769918-4131bdc6-502e-4ec9-b36b-3867f3b74a8e](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/11605865-ec8b-43b4-aa83-4d3d83dda1dc)
## MEDIAN
![241769951-6844e74b-4807-45c9-8068-bd1a988c1ab4](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/78385b32-3e8f-44e7-ba12-d2d476a51066)
## VALUE METHOD
![241770032-2b6e5f5e-7f6d-4022-b04e-ae2e977295ef](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/06cd01dc-2bd0-4003-a558-3712e7a520ce)
## BACKWARD METHOD
![241770057-8b9717a2-922e-4ce8-9b30-68029d6d3140](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/13807313-f502-4333-8c64-e2d402c37998)
## DUPLICATES
![241770120-3b747bf6-faba-4cb2-8b83-d72cfc8c95e1](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/7b43b4eb-b207-47f0-92db-d0a2bd09e271)
## INFO AFTER CLEANING
![241770174-fe38cb97-eeef-488c-8f62-2764300bdc23](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/fbf9905a-f109-4475-9f6e-b4a70f0cb770)
## isnull().sum() after cleaning
![241770272-173a3c67-5c37-44b6-a800-3acd6c70401e](https://github.com/SASIRAJ27/ODD2023-Datascience-Ex01/assets/113497176/56690568-8456-44cb-8b76-798cdab64841)
## RESULT:
Thus the given data is read,cleansed and cleaned data is saved into the file.
