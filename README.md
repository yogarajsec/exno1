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
df=pd.read_csv('/content/Data_set (1).csv')
df
```
![Screenshot 2025-03-08 112354](https://github.com/user-attachments/assets/abbc65fd-0232-4e2f-b102-40fa762c6666)
```
df.info()
```
![Screenshot 2025-03-08 114013](https://github.com/user-attachments/assets/c90cb990-8e44-46fc-9ff1-2e356f1b552e)

```
df.describe()
```
![Screenshot 2025-03-08 114019](https://github.com/user-attachments/assets/e049c7f1-2917-447f-9bc1-262490d6b0cb)


```
df.head(10)
```
![Screenshot 2025-03-08 114047](https://github.com/user-attachments/assets/6480bbf8-5f8e-4314-bd1f-417a1676be13)

```
df.tail(5)
```
![Screenshot 2025-03-08 114056](https://github.com/user-attachments/assets/a46e3f4f-bf23-4351-b524-63af6a8d196c)

```
df.shape
```
![Screenshot 2025-03-08 114101](https://github.com/user-attachments/assets/0170dcca-010c-4ca8-8246-054353ef6df1)

```
df.isnull()
```
![Screenshot 2025-03-08 114109](https://github.com/user-attachments/assets/4e51fae5-b7c4-4d16-bb68-a7de1afd18ce)
```
df.notnull()
```
![Screenshot 2025-03-08 114120](https://github.com/user-attachments/assets/8e150e31-ad55-4963-a86c-be45bceb4e94)
```
df.isnull().sum()
```
![Screenshot 2025-03-08 114127](https://github.com/user-attachments/assets/1149bb31-c721-4a44-a366-828d1ad4a84f)
```
df.dropna(axis=0)
```
![Screenshot 2025-03-08 114135](https://github.com/user-attachments/assets/a25703ad-c750-42a3-aada-257ddf6088ad)
```
df.dropna(axis=1)
```
![Screenshot 2025-03-08 114144](https://github.com/user-attachments/assets/2343ef9e-0553-4470-9e08-31ea750508ee)
```
dfs=df[df['num_episodes']>20]
dfs
```
![Screenshot 2025-03-08 114157](https://github.com/user-attachments/assets/2f381d06-6aed-42e9-8f0d-ef14fd136b4c)
```
df.fillna(0)
```
![Screenshot 2025-03-08 114207](https://github.com/user-attachments/assets/39707c86-f413-425f-bbca-f0e4c879a65b)

```
dfs=df[df['show_name'].str.startswith(('A','F'))&(df['num_episodes']>25)]
dfs
```
![Screenshot 2025-03-08 114214](https://github.com/user-attachments/assets/5eb3ce85-d9b4-45ee-a333-6a7fba393907)
```
df.iloc[:3]
```
![Screenshot 2025-03-08 114234](https://github.com/user-attachments/assets/6e65a132-9241-4413-9013-63a584c0412a)
```
df.iloc[:4]
```
![Screenshot 2025-03-08 114247](https://github.com/user-attachments/assets/42177c7f-19d3-495d-ae9e-8063d1621c58)
```
df.iloc[[1,3,5],[1,3,5]]
```
![Screenshot 2025-03-08 114257](https://github.com/user-attachments/assets/31ba4af8-28b0-4177-a7bf-d404b089b5ec)

```
df.fillna('sample value')
```
![Screenshot 2025-03-08 114306](https://github.com/user-attachments/assets/52526f1a-c35d-4eb5-934b-824b32be28c3)
```
ffil=df.fillna(method='ffill')
ffil
```
![Screenshot 2025-03-08 114317](https://github.com/user-attachments/assets/bf82c50d-4ded-4334-a613-9758f8b6048e)
```
bfil=df.fillna(method='bfill')
bfil
```
![Screenshot 2025-03-08 114329](https://github.com/user-attachments/assets/9b5ca059-5459-4751-808e-beb5171c03da)
```
m = df.num_episodes.mean()
m
```
![Screenshot 2025-03-08 114342](https://github.com/user-attachments/assets/736bc86d-7bdf-4bbe-b98f-9f1e2873704c)
```
m= df.fillna(df['num_episodes'].mean())
m
```
![Screenshot 2025-03-08 114355](https://github.com/user-attachments/assets/c2934920-1925-4e8a-902a-243fd03c37e6)
```
fmean=df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
fmean
```
![Screenshot 2025-03-08 114403](https://github.com/user-attachments/assets/bed03267-8cfc-490a-b4b2-a8de6f132229)
```
df=pd.read_csv('/content/SAMPLEIDS.csv')
df
```
![Screenshot 2025-03-08 114416](https://github.com/user-attachments/assets/262aec0e-cb43-442f-842b-e0960543c69a)
```
df.shape
```
![Screenshot 2025-03-08 114422](https://github.com/user-attachments/assets/6156a00b-3397-4bb5-82c3-c61f3a410b15)
```
df.describe()
```
![Screenshot 2025-03-08 114428](https://github.com/user-attachments/assets/9caab11f-1307-403a-85e8-ca3a0b5c1076)

```
df.info()
```
![Screenshot 2025-03-08 114434](https://github.com/user-attachments/assets/400c3911-f468-4ec0-863d-d632c25fc45b)
```
df['GENDER'].value_counts()
```
![Screenshot 2025-03-08 114440](https://github.com/user-attachments/assets/9594e310-e899-4522-954b-dd0ae9257114)
```
df.dropna(haow='any').shape
```
![Screenshot 2025-03-08 114444](https://github.com/user-attachments/assets/da692e20-4ba1-41e8-a749-0a1e3fdaee2a)
```
x1=df.dropna(how='any')
x1
```
![Screenshot 2025-03-08 114451](https://github.com/user-attachments/assets/d08c469f-c858-4190-953b-04597c7e85a9)
```
res =df.dropna(subset=['M1','M2','M3','M4'],how='any')
res
```
![Screenshot 2025-03-08 114458](https://github.com/user-attachments/assets/d2ff63a3-e80f-434b-9d56-ff938c340b69)
```
m2=df.TOTAL.mean()
m2
```
![Screenshot 2025-03-08 114504](https://github.com/user-attachments/assets/c973c2a1-5617-4ce6-9ff9-710006f6f9f8)
```
df.TOTAL.fillna(m2,inplace=False)
```
![Screenshot 2025-03-08 114512](https://github.com/user-attachments/assets/c8eb6400-a868-42a1-87a8-c7c3546c7266)

# Result
          <<include your Result here>>

