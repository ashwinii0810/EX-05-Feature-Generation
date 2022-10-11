# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE
import pandas as pd

df=pd.read_csv("/content/data[1].csv")

df.info()

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['Ord_2'] = le.fit_transform(df['Ord_2'])

sns.set(style ="darkgrid")

sns.countplot(df['Ord_2'])

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['City']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['City'], axis=1)

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])

df.head(10)


df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])

df.head(10)
# OUPUT
![image](https://user-images.githubusercontent.com/95408674/195148645-3ff4ab68-ff5a-4da8-954e-bca5a8a38273.png)

![image](https://user-images.githubusercontent.com/95408674/195148748-b12c3570-5b8a-4519-9d53-7d5711373d43.png)

![image](https://user-images.githubusercontent.com/95408674/195148831-c2a2f359-35d6-43d8-911a-a4c9b05f8a60.png)

![image](https://user-images.githubusercontent.com/95408674/195148929-e2de4a74-9dc8-4f52-8914-a4c5681e02a5.png)

![image](https://user-images.githubusercontent.com/95408674/195149029-8c702639-c298-4081-9829-361e665f8655.png)

encoding dataset

![image](https://user-images.githubusercontent.com/95408674/195150047-76d3aa8a-76a5-441e-b358-052cf146409f.png)

![image](https://user-images.githubusercontent.com/95408674/195150160-2716c263-ff52-4028-8605-afe87d33956d.png)

![image](https://user-images.githubusercontent.com/95408674/195150255-14a1faa2-236d-4f3c-b2b5-f002fe22028c.png)

![image](https://user-images.githubusercontent.com/95408674/195152628-d4d8a827-209b-4f6d-a26c-dbc874d6f552.png)

![image](https://user-images.githubusercontent.com/95408674/195154452-32d6ac57-0161-4651-9e07-7c2bd9c6411a.png)

![image](https://user-images.githubusercontent.com/95408674/195154513-4c2fd80a-309b-4593-8701-1e1034a06e18.png)

![image](https://user-images.githubusercontent.com/95408674/195154582-e7b82dc8-8f59-4c37-9f28-18a1c110e9b4.png)

![image](https://user-images.githubusercontent.com/95408674/195154666-cc40068b-f3c9-49ab-8ce1-edc81bed5718.png)

![image](https://user-images.githubusercontent.com/95408674/195154764-ef56774a-b5f1-4df0-b916-1c0920efb8d2.png)

![image](https://user-images.githubusercontent.com/95408674/195154840-7ac74ada-8bf4-4540-8aaa-8d2dd13810da.png)

![image](https://user-images.githubusercontent.com/95408674/195154928-5ee98165-7c20-4f1e-be39-ce0d449f3190.png)















