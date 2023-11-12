# ODD2023-Datascience-Ex-04
# Aim:
To perform Multivariate EDA on the given data set.
# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
# Alogorithm:
STEP 1:
Import the built libraries required to perform EDA and outlier removal.

STEP 2:
Read the given csv file

STEP 3:
Convert the file into a dataframe and get information of the data.

STEP 4 :
Return the objects containing counts of unique values using (value_counts()).

STEP 5 :
Plot the counts in the form of Histogram or Bar Graph.

STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8:
Save the final data set into the file.
# Program:
```py
Name : Kanishka.V.S
Register Number : 212222230061
```
# SuperStore.csv file:
```py
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
# diabetes.csv file:
```py
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes.csv")
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
# Output:
# Superstore:
##DATA FRAME OF SUPERSTORE:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/8c27c82e-4992-4c46-a336-3c6c11c2615d)
##Data information
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/60296c37-72a4-428a-a4e0-52b1ca1ac035)
##Data describing:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/364a5bad-a9a3-4669-9cf1-fed9874d8191)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/3bb6ae62-1a6d-4e38-8129-76af4c19b9c2)
##After removing null values:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/d1e75b06-0ef3-467b-a55c-7e7550919fa2)
##Scatter plot:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/46d31bf8-c060-4eb5-8ddb-6986daf039ac)
##Bar plot:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/45d0b809-3631-412a-948d-f1a821e17860)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/dabf7873-bf7b-4911-a1d2-d2314e59bb58)
##BoxPlot:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/609efe51-9d0d-4a09-a89b-f377f36b8c77)
##Distplot:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/9e1d73da-9df8-4ea2-85b1-a44d0cab6e05)
##Correlation coefficient interpretation:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/13b8ac6e-677c-473f-b15f-f4a3cce2cbda)
##Heatmap:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/9beb511d-d109-44f0-ae81-9913b4e37dd5)
## DIABETES:
##DATA FRAME FOR DIABETES:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/a86db36f-4bcd-4dcd-bba1-ca26c7eddfb0)
##Data information1:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/6261047e-0e5e-43d2-a6bc-53bc71f8b710)
##Data describing:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/caa9b5d0-506a-473e-8577-1ed50eddf466)
##Sum of null values:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/0353c734-9a8b-406c-91ac-b1e7039923b3)
##Scatter plot:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/4609c2b6-21e2-40e8-9e68-b6e254cce6b7)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/6477eb50-f51c-49e3-b9a5-fd0a06e75117)
##Barplot:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/bf7cfdcd-e246-4684-9524-4ba747bc60fd)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/f6ba329f-d753-44bf-aa59-483f0479dca5)
##Boxplot:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/ecec711c-9d9a-4e34-9595-9cd858a58da4)
##Distplot:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/a59a4462-109c-435d-bf63-edbc2f940528)
##correlation coefficient interpretation:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/6c0fba6a-4924-4d00-a54e-eab0135be208)
##Heatmap:
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-04/assets/113497357/262f4c4f-3eee-45a0-a463-f7ed5e7cd86d)
## Result:
Thus we have read the given data and performed the multivariate analysis with different types of plots.
