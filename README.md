# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

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

NAME: DHIVYAPRIYA.R

REGISTER NO.:212222230032

Data Preprocessing

import seaborn as sns

import pandas as pd

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

print(df)

df.isnull().sum()

Handling Outliers

plt.figure(figsize=(8,8))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

Removing Outliers

plt.figure(figsize=(8,8))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

1) Which day of the week has the highest total bill amount?

sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])

plt.legend(loc="center")

plt.title("Highest Total Bill Amount by day of the week")

plt.show()

2) What is the average tip amount given by smokers and non-smokers?

sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

3) How does the tip percentage vary based on the size of the dining party?

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

4) Which gender tends to leave higher tips?

sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])

plt.title("Tips based on gender")

5) Is there any relationship between the total bill amount and the day of the week?

sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])

plt.legend(loc="best")

plt.title("Total bill amount by day of the week")

6) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

7) Which dining party size group tends to have the highest average total bill amount?

sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

8) What is the distribution of tip amounts for each day of the week?

sns.boxplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

9) How does the tip amount vary based on the type of service (lunch vs. dinner)?

sns.violinplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

10) Is there any correlation between the total bill amount and the tip amount?

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()

# OUPUT
![Screenshot 2023-05-19 110739](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/35017402-cb67-4f50-b126-65425c8ccc0f)
![Screenshot 2023-05-19 110814](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/690d7898-273f-421e-8a6a-7680a13fb636)
![Screenshot 2023-05-19 110831](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/a8d62d55-8b5c-43e4-85e4-9cb390047e0a)
![Screenshot 2023-05-19 110846](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/8503dc07-468d-45b9-bb01-943c98c22978)
![Screenshot 2023-05-19 110901](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/e43eeb9d-4f43-4550-a7a3-11d4d1e5cbd9)
![Screenshot 2023-05-19 111003](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/25ad6627-6d27-4053-9c4b-849e132120da)
![Screenshot 2023-05-19 111012](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/a42ada6c-99fa-4f51-beb4-a068e7f28f41)
![Screenshot 2023-05-19 111021](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/d0f105a2-9bae-4996-b270-22345fa500cd)
![Screenshot 2023-05-19 111032](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/3889d917-9ae8-499c-bfbf-e102169921f0)
![Screenshot 2023-05-19 111120](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/cd4240fe-00ad-4a1b-996c-2b71009b0c9c)
![Screenshot 2023-05-19 111137](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/2841f51f-8d78-48c6-bd59-2c1b9cdc0d7c)
![Screenshot 2023-05-19 111148](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/ca6f2727-46d5-4303-a1ea-c5d7f7893b6e)
![Screenshot 2023-05-19 111312](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/fc420faf-b183-4ed8-ad3d-107d0617cde4)
![Screenshot 2023-05-19 111331](https://github.com/dhivyapriyar/Ex-08-Data-Visualization-/assets/119477552/4ac650fa-d85e-412b-ab99-675fd847b3ea)

