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





