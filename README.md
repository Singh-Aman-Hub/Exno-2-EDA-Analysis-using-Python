# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
# Reg no: 212224040020 || Name: Aman Singh
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
        Python codes:
      
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

dt=pd.read_csv("/content/titanic_dataset.csv")
dt

dt.info()

dt.describe()

dt.shape

dt.set_index("PassengerId",inplace=True)

dt

dt.nunique()

dt.Survived.value_counts()

pt=(dt.Survived.value_counts()/dt.shape[0]*100).round(2)
pt

sns.countplot(data=dt,x="Survived")

dt

dt.Pclass.unique()

dt.rename(columns={'Sex':'Gender'},inplace=True)

sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=6,aspect=.7);

sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")

dt.boxplot(column="Age",by="Survived")

sns.scatterplot(x=dt["Age"],y=dt["Fare"])

sns.jointplot(x="Age",y="Fare",data=dt)

Fig,ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)

sns.catplot(col="Survived",x="Gender",hue="Pclass",kind="count",data=dt)

corr = dt.select_dtypes(include=np.number).corr()
sns.heatmap(corr, annot=True,)

sns.pairplot(dt)


      Codes with corresponding outputs:
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 00 PM" src="https://github.com/user-attachments/assets/11b656a1-d672-4ca6-b47f-dbcea0267a14" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 07 PM" src="https://github.com/user-attachments/assets/d66a3762-c685-4bf3-9402-58585052d546" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 11 PM" src="https://github.com/user-attachments/assets/7095cfc6-cfd9-4998-bc42-2dd91b65f648" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 16 PM" src="https://github.com/user-attachments/assets/fce084ba-0c3a-4467-8d48-45116b041d97" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 20 PM" src="https://github.com/user-attachments/assets/435a9ea0-36b3-4160-a151-b73c452c9872" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 25 PM" src="https://github.com/user-attachments/assets/ebbfd357-27d4-4271-9e64-325d0dc74176" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 29 PM" src="https://github.com/user-attachments/assets/64250432-92e7-443b-8989-17f1943553ae" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 34 PM" src="https://github.com/user-attachments/assets/2a6c98e8-14b7-4984-8fde-17bd74029d43" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 38 PM" src="https://github.com/user-attachments/assets/47c86c30-4945-41d8-b585-16e6903b7178" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 04 43 PM" src="https://github.com/user-attachments/assets/7901e494-c96b-4a6e-9818-e105822f6b33" />
<img width="1440" alt="Screenshot 2025-04-14 at 1 05 07 PM" src="https://github.com/user-attachments/assets/3e2c6cde-6d7c-4e97-8ad2-13db4e810b2a" />



# RESULT
        Hence Exploratory Data Analysis were perfomed successfully on the given data set.












