## EX-NO 06-DATA VISUALIZATION USING SEABORN LIBRARY

### Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

### EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

### Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

### Coding and Output:
```
# Step 1: Import necessary libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
# Set visualization style
sns.set(style="whitegrid")
plt.rcParams['figure.figsize'] = (10, 6)
# Step 2: Load the Titanic dataset
df = sns.load_dataset("titanic") # Alternatively: pd.read_csv("your_path/titanic.csv")
print("Dataset Loaded Successfully!\n")
print(df.head())

```
### output
```
Dataset Loaded Successfully!

   survived  pclass     sex   age  sibsp  parch     fare embarked  class  \
0         0       3    male  22.0      1      0   7.2500        S  Third   
1         1       1  female  38.0      1      0  71.2833        C  First   
2         1       3  female  26.0      0      0   7.9250        S  Third   
3         1       1  female  35.0      1      0  53.1000        S  First   
4         0       3    male  35.0      0      0   8.0500        S  Third   

     who  adult_male deck  embark_town alive  alone  
0    man        True  NaN  Southampton    no  False  
1  woman       False    C    Cherbourg   yes  False  
2  woman       False  NaN  Southampton   yes   True  
3  woman       False    C  Southampton   yes  False  
4    man        True  NaN  Southampton    no   True  
```
```
# Step 3: Visualize missing values using a heatmap
plt.figure(figsize=(10, 6))
sns.heatmap(df.isnull(), cbar=False, cmap='viridis', yticklabels=False)
plt.title("Missing Values Heatmap")
plt.show()
# Step 4: Countplot - Number of passengers by gender
sns.countplot(x='sex', data=df, palette='Set2')
plt.title("Count of Passengers by Gender")
plt.xlabel("Sex")
plt.ylabel("Count")
plt.show()
```
<img width="794" height="621" alt="image" src="https://github.com/user-attachments/assets/164cb0b2-cea8-4ad6-bb74-8f7ac091689e" />
<img width="860" height="556" alt="image" src="https://github.com/user-attachments/assets/8640d616-81e2-4466-a29b-4585d9f5583d" />

```
# Step 5: Countplot - Survival status by passenger class
sns.countplot(x='survived', hue='pclass', data=df, palette='Set1')
plt.title("Survival Count by Passenger Class")
plt.xlabel("Survived (0 = No, 1 = Yes)")
plt.ylabel("Count")
plt.legend(title='Pclass')
plt.show()
# Step 6: Histogram - Distribution of passenger ages
sns.histplot(data=df, x='age', kde=True, bins=30, color='skyblue')
plt.title("Age Distribution of Passengers")
plt.xlabel("Age")
plt.ylabel("Frequency")
plt.show()
# Step 7: Boxplot - Age vs Passenger Class
sns.boxplot(x='pclass', y='age', data=df, palette='pastel', hue='pclass', legend=False)
plt.title("Age Distribution Across Passenger Classes")
plt.xlabel("Passenger Class")
plt.ylabel("Age")
plt.show()
# Step 8: Pairplot - Relationships among numerical features
sns.pairplot(df[['age', 'fare', 'pclass', 'survived']], hue='survived', palette='coolwarm')
plt.suptitle("Pairwise Relationships", y=1.02)
plt.show()
# Step 9: Correlation heatmap
corr = df.corr()
sns.heatmap(corr, annot=True, cmap='Blues', linewidths=0.5)
plt.title("Correlation Matrix Heatmap")
plt.show()
```
<img width="860" height="556" alt="image" src="https://github.com/user-attachments/assets/3f475ee7-076c-45ad-92eb-24a8a1bb80a7" />
<img width="851" height="556" alt="image" src="https://github.com/user-attachments/assets/2a5ad19a-60f6-4089-86f4-9b0ee461fa9f" />
<img width="851" height="556" alt="image" src="https://github.com/user-attachments/assets/c2c3ec08-1794-40fb-81d9-75187c440660" />
<img width="829" height="769" alt="image" src="https://github.com/user-attachments/assets/a34b21fa-b53f-42f4-a38f-5d93ab19b907" />
<img width="849" height="533" alt="image" src="https://github.com/user-attachments/assets/fb59798c-bd0d-49af-9c16-ffa0777ce839" />


### Result:
Thus, the program to perform data visualization using the Seaborn Python library was successfully implemented. Various visualization techniques such as heatmap, countplot, histogram, boxplot, pairplot, and correlation matrix were used to analyze the dataset. These visualizations helped in identifying missing values, understanding data distribution, detecting outliers, and analyzing relationships between different features effectively.

