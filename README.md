# Ex-04: Multivariate Analysis:
### Date:
## AIM:
To perform Multivariate EDA on the given data set.

## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
### STEP 01:
Import the built libraries required to perform EDA and outlier removal.

### STEP 02:
Read the given csv file

### STEP 03:
Convert the file into a dataframe and get information of the data.

### STEP 04:
Return the objects containing counts of unique values using (value_counts()).

### STEP 05:
Plot the counts in the form of Histogram or Bar Graph.

### STEP 06:
Use seaborn the bar graph comparison of data can be viewed.

### STEP 07:
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 08:
Save the final data set into the file.

## PROGRAM:
### Superstore CSV File:
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (1).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)
```

### Diabetes CSV File:
```python

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes (1).csv")
df
df.describe()
df.info
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
```
## Output:
### SUPERSTORE OUTPUT:
![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/6e4625c0-d82d-466b-9c57-f61f81585929)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/05f5a5d5-7921-428c-94c3-73a1f87b4acd)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/7adb009a-c13b-4680-96ae-8b417d72abbe)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/b6888e36-6d1d-4cc3-9457-902465e2fc1e)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/cfe8ad34-0864-4bc5-a1ee-2fd25f0437e8)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/8b764560-4f3f-440f-b9c7-0ffc7c8bbd54)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/6c22a57c-fbee-4381-bce7-93712457f3ac)

### DIABETES OUTPUT:

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/f1524e9f-1f7f-4a6a-aa65-5eeaccfd3c87)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/2b614c56-0c1f-456d-8366-b572849f7e78)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/7fc72b20-02df-4ac6-b513-032ffd66e23a)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/e83d2297-61a4-4a2e-953a-bd5ce80f8bb3)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/90454b7a-3142-4d3b-b3ca-de2d744a9ff0)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/f6f7abc8-b1a0-478d-afb5-4d8c8e2243f3)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/6dbc7f9e-58f8-48cd-9b58-94cc2566f704)

![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex-04/assets/94164665/6fb132f4-3b7e-4eb5-89ae-744978493a97)


## Result:
Thus we have read the given data and performed the multivariate analysis with different types of plots.

