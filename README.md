# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:

Dev by : KARTHICK S

Reg by : 212224230114

```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

sns.lineplot(x=x,y=y)
```
## Output:
![image](https://github.com/user-attachments/assets/a494defc-1cf4-43ca-9da1-1f753364e08e)

```
df = sns.load_dataset("tips")
df
```
## Output:
![image](https://github.com/user-attachments/assets/49fec9e6-e275-413a-877b-65cca2cf35c6)

```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
## Output:
![image](https://github.com/user-attachments/assets/bab2929a-f61a-4283-8136-ecb3906be75b)

```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]

sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
## Output:
![image](https://github.com/user-attachments/assets/390a0b59-d35d-445a-bd46-37c05c9ed11b)

```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
## Output:
![image](https://github.com/user-attachments/assets/43919f19-ce49-4a22-9595-750955faa66b)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
## Output:
![image](https://github.com/user-attachments/assets/01ffc713-663f-44d8-9acb-ab5abb8b0417)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]

plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
## Output:
![image](https://github.com/user-attachments/assets/e5d48ff3-bc22-428d-a958-6cb3af1b757c)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
## Output:
![image](https://github.com/user-attachments/assets/26101c88-4284-4016-b631-5d68d87c27b7)

```
tit=pd.read_csv("/content/titanic_dataset.csv")
tit
```
## Output:
![image](https://github.com/user-attachments/assets/8ed2050d-9aad-42bc-a1d7-fd9807f35295)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
## Output:
![image](https://github.com/user-attachments/assets/91e49711-1deb-42ab-8a50-45fe36779abf)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
## Output:
![download](https://github.com/user-attachments/assets/61b14dfb-0f7e-450b-a171-8adbcb6787d7)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
## Output:
![image](https://github.com/user-attachments/assets/5b4c48c5-ce62-43fc-842b-205893a1415d)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
## Output:
![image](https://github.com/user-attachments/assets/bfe5a256-ca90-4561-a351-6020f37a1477)

```
sns.histplot(data = num_var, kde = True)
```
## Output:
![image](https://github.com/user-attachments/assets/148b0f62-3543-493b-97fa-033bddac8bbe)

```
df=pd.read_csv("/content/titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
## Output:
![image](https://github.com/user-attachments/assets/d8c58d29-2efd-4147-b242-ed22cb4bfdad)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
## Output:
![image](https://github.com/user-attachments/assets/f9bbc174-5b76-4a9c-956f-e065e47facc7)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
## Output:
![image](https://github.com/user-attachments/assets/64cb14f9-2509-4962-bb56-2ab16110d0ce)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
## Output:
![image](https://github.com/user-attachments/assets/fa104fe8-8485-4bdb-a67b-013540f70d32)
```

mart=pd.read_csv("/content/titanic_dataset.csv")
mart
```
## Output:
![image](https://github.com/user-attachments/assets/049b44be-3f4f-4ed5-8bb7-c08ef69523e0)

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```
## Output:
![image](https://github.com/user-attachments/assets/bdaaa550-e063-4a9d-86de-bcf8f09ac728)

```
sns.kdeplot(data=mart,x='PassengerId')
```
## Output:
![image](https://github.com/user-attachments/assets/4554ebbc-2508-4c26-9a65-fe60b17915a1)

```
sns.kdeplot(data=mart,x='Age')
```
## Output:
![image](https://github.com/user-attachments/assets/85314a75-0daa-4f90-91de-24eb6aa09f15)

```
sns.kdeplot(data=mart)
```
## Output:
![image](https://github.com/user-attachments/assets/10adf1b1-228f-43c9-b1e9-2d4399393c26)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
## Output:
![image](https://github.com/user-attachments/assets/6369e339-371d-4cd8-9e59-d822676269d1)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
## Output:
![image](https://github.com/user-attachments/assets/ced67352-aaa6-4c38-858b-9bcaadd8d8b6)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
## Output:
![image](https://github.com/user-attachments/assets/10cc22b1-262e-4b5b-97f0-0d5fed1eae78)
```
hm=sns.heatmap(data=data)
```
## Output:
![image](https://github.com/user-attachments/assets/c0cb5b09-2cc9-493f-8d7f-c09602179988)



# Result:

Data visualization using seaborn was done successfully
