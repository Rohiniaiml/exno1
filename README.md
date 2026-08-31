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
import pandas as pd
import numpy as np

df=pd.read_csv("/content/SAMPLEIDS.csv")

df
<img width="1523" height="760" alt="image" src="https://github.com/user-attachments/assets/05cf4616-681b-4c04-990b-430c4282d962" />
df.isnull()
<img width="889" height="614" alt="image" src="https://github.com/user-attachments/assets/41eef823-b62d-4a8d-b6f0-760daf90ca92" />
df.shape
<img width="1042" height="466" alt="image" src="https://github.com/user-attachments/assets/ff38c8ac-9f10-4024-9252-912baad8c501" />
df.head(3)
<img width="1075" height="192" alt="image" src="https://github.com/user-attachments/assets/f00d6185-87c7-46ca-98e2-233e00d42179" />
df.tail(3)
<img width="1202" height="199" alt="image" src="https://github.com/user-attachments/assets/80097e08-310a-4517-aed8-7de9b2865664" />
df.isnull().sum()
<img width="334" height="582" alt="image" src="https://github.com/user-attachments/assets/49239d45-ebc2-488e-8251-b9fd2ed244c7" />
df.dropna(how='any').shape
<img width="167" height="58" alt="image" src="https://github.com/user-attachments/assets/8d924395-6bf2-4832-a0f6-b888c46d22f7" />
s1=df.dropna(how='all').shape

s1
<img width="145" height="40" alt="image" src="https://github.com/user-attachments/assets/98179b16-a093-4b19-949f-0e10afbc885f" />
tot=df.dropna(subset=['TOTAL'],how='any')
tot
<img width="1281" height="631" alt="image" src="https://github.com/user-attachments/assets/6fc607a8-6fd0-417b-a0b5-d59453fabe12" />
mn=df.TOTAL.mean()
mn
<img width="314" height="78" alt="image" src="https://github.com/user-attachments/assets/44e3e9d6-bef9-4e02-b1f3-64865a6ac830" />
df.TOTAL.fillna(mn,inplace=True)
<img width="1356" height="179" alt="image" src="https://github.com/user-attachments/assets/1bc32722-4a23-42f2-9408-8a9959997769" />
df.isnull().sum()
<img width="383" height="579" alt="image" src="https://github.com/user-attachments/assets/76c73d86-f13c-40fb-91c8-0f789da76dba" />

df['M1'].fillna(method='ffill',inplace=True)
<img width="1318" height="238" alt="image" src="https://github.com/user-attachments/assets/c1c77666-1800-4cd1-a97b-a3c20463e52a" />
df.drop_duplicates(inplace=True)
df

<img width="1166" height="623" alt="image" src="https://github.com/user-attachments/assets/fb0987cf-9300-4a4e-9be8-f49f0767b084" />
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
<img width="693" height="639" alt="image" src="https://github.com/user-attachments/assets/ed3e2904-66f0-47b7-9623-1d9f4043b560" />

df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
<img width="757" height="626" alt="image" src="https://github.com/user-attachments/assets/78f3be47-f540-47fa-b3aa-df9a45ecbf5a" />

outlier didection

import pandas as pd
import seaborn as sns
import numpy as np
age = [1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
<img width="346" height="612" alt="image" src="https://github.com/user-attachments/assets/bc3ec8a3-923c-4141-b806-b005270c1e34" />
sns.boxplot(data=af)
<img width="831" height="534" alt="image" src="https://github.com/user-attachments/assets/3a549b30-33b5-407b-b3c4-068ed6411d68" />
sns.scatterplot(data=af)



            <<include your coding and its corressponding output screen shots here>>
# Result
          <<include your Result here>>
