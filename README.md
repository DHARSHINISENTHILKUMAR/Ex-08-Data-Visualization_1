# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
~~~
import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

df.head()

df.isnull().sum()

plt.figure(figsize=(5,5))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(5,5))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

sns.barplot(x=df['day'], y=df['total_bill'])

plt.title("Highest Total Bill Amount by day")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'],hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

plt.show()

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.barplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

plt.show()

sns.barplot(x=df['sex'], y=df['tip'])

plt.title("Highest tips based on gender")

plt.show()

sns.barplot(x=df['day'],y=df['total_bill'])

plt.title("Total bill amount by day of the week")

plt.show()

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.barplotdata=df,(x=df['size'],y=df['total_bill'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

sns.violinplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.barplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()
~~~

# OUPUT
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/4d51abee-c87a-45bd-ac44-5ef97a39b2d5)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/05c2d45f-466d-4ec0-a910-6544428a8229)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/8d1ae9da-94db-4a7d-8308-a237268cf023)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/7ac6747c-1996-4112-9353-e811e27865ac)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/85cd88ea-3b99-447d-aba8-af5d5bad8894)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/de75a012-f7d2-4526-9ec7-c4d47efb47b8)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/25377265-cd14-480a-9757-832ebe00f450)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/25e5bfe9-bab7-4b92-985c-c801ad7ea903)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/74170bd5-b34f-4077-92e1-23a4c4e116f3)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/53c691de-6be8-4786-9439-01917a136ce1)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/9918ae0d-307e-4c1f-bae7-4f991741d7ef)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/fddc9bbe-6b3e-438c-97d5-3d1d0db46b47)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/d06757c6-2808-4546-ab18-e3084f773762)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization_1/assets/113699377/ba1fa399-c99f-4ba8-95b6-e3d9cc56f327)

#Result:
~~~
Thus data visualization on complex dataset was performed successfully.
~~~
