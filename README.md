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
 from google.colab import drive
drive.mount('/content/drive')

ls drive/MyDrive/'Colab Notebooks'/

tit = pd.read_csv("drive/MyDrive/Data Science/titanic_dataset.csv")
print(tit.head()) 

![image](https://github.com/user-attachments/assets/abb1894c-3767-445f-855c-28a962d29fc6)

print(tit.columns)

![image](https://github.com/user-attachments/assets/d3ffa15d-63c3-4f5a-9311-d609a828db42)

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)

![image](https://github.com/user-attachments/assets/0d6e0a51-cfef-4b44-b984-9a6b5710b17c)

x = [1, 2, 3, 4, 5]
y1 = [3, 5, 2, 6, 1]
y2 = [1, 6, 4, 3, 8]
y3 = [5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")

![image](https://github.com/user-attachments/assets/bac71c09-5b88-470c-bc7e-e22e5678b710)

# **Bar Plot - Seaborn**

tips = sns.load_dataset('tips')

avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()

![image](https://github.com/user-attachments/assets/e1d91e58-0609-4b6a-9fce-1d23e2c58349)

avg_total_bill = tips.groupby('time')['total_bill'].mean() 
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)

![image](https://github.com/user-attachments/assets/d70bf8b9-93b9-4575-8a8a-6dbe5811a709)

plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow') 
plt.title("Fare of Passenger by Embarked Town")

![image](https://github.com/user-attachments/assets/a74b0b2c-dcd5-4abe-8b9c-d2632c7152b7)

plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass') 
plt.title("Fare of Passenger by Embarked Town, Divided by Class")

![image](https://github.com/user-attachments/assets/c4f18b12-6439-41f2-b464-53a9e44e057f)

tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')

![image](https://github.com/user-attachments/assets/205a0d47-bb55-4750-890e-f18f368f6fa3)

# **VIOLIN PLOT**

sns.violinplot(data=tit, x='Survived', y='Age', hue='Sex', split=True, palette='muted')
plt.title('Age Distribution by Survival Status and Gender')
plt.xlabel('Survived (0 = No, 1 = Yes)')
plt.ylabel('Age')

![image](https://github.com/user-attachments/assets/1a9fdda8-881b-41d1-b9a4-77e15594559d)

# **HISTOGRAM**

np.random.seed(0)
marks = np.random.normal(loc=70, scale=10, size=100)

np.random.seed(1)
num_var = np.random.randn(1000)
num_var = pd.Series(num_var, name = "Numerical Variable")
num_var

![image](https://github.com/user-attachments/assets/7e7cf402-3132-4df8-830e-7435606746e1)

sns.histplot(data = num_var, kde = True)

![image](https://github.com/user-attachments/assets/9a457840-9068-4015-8643-833888573dbe)

sns.histplot(data=tit,x="Pclass", hue="Survived", kde=True)

![image](https://github.com/user-attachments/assets/8c253055-631c-4c8c-9b68-5505e0d3f32e)

# **Others**

tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])

![image](https://github.com/user-attachments/assets/b36f0380-669a-47fb-89a4-1ccf01bbf5be)

sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightgray", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})

![image](https://github.com/user-attachments/assets/6e130d2e-5fa3-4d2c-ab1b-c0cc56a48a75)

sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")

![image](https://github.com/user-attachments/assets/7fe28e3b-7801-4249-954d-2ff641452ad8)

mart=tit[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']] 
sns.kdeplot(data=mart,x='PassengerId')

![image](https://github.com/user-attachments/assets/6b68ede7-46ef-4eeb-854a-17530413e9f9)

sns.kdeplot(data=mart,x='Age')

![image](https://github.com/user-attachments/assets/293bc680-aa05-407f-9bc2-5c5cd2f8fdd2)

sns.kdeplot(data=mart)

![image](https://github.com/user-attachments/assets/b24317a3-0242-474c-90a0-556f18addeb5)

sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')

![image](https://github.com/user-attachments/assets/c7640e61-0cb8-48e1-ac18-37fda20510d7)

sns.kdeplot(data=mart,x='PassengerId',y='Survived')

![image](https://github.com/user-attachments/assets/f4414d35-401d-4f82-9187-f285e82fffce)

data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)

![image](https://github.com/user-attachments/assets/6b361ef8-3f84-4fc9-b31f-ea94cf22b371)

# Result:
 Include your result here
