# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
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
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
<img width="1463" height="503" alt="Screenshot 2025-09-15 221240" src="https://github.com/user-attachments/assets/4d060fde-de40-41e4-97c8-b2e4f13f7732" />

```

df.info()

```

<img width="456" height="414" alt="Screenshot 2025-09-15 221416" src="https://github.com/user-attachments/assets/7b485e36-7445-49ac-bfcb-40ceed996165" />

```

df.dtypes

```

<img width="240" height="546" alt="Screenshot 2025-09-15 221541" src="https://github.com/user-attachments/assets/8b544587-c3c8-4364-8112-0cc5d4f3dfdd" />

```

df.describe()


```

<img width="931" height="365" alt="Screenshot 2025-09-15 221658" src="https://github.com/user-attachments/assets/03b5c197-05fa-456a-b0ca-cd0b54a2e3c1" />


```

df.shape


```


<img width="119" height="38" alt="Screenshot 2025-09-15 221809" src="https://github.com/user-attachments/assets/3677209c-f1fd-4199-840c-2366aeedf042" />


```

df.value_counts()


```

<img width="1497" height="537" alt="Screenshot 2025-09-15 221925" src="https://github.com/user-attachments/assets/0f6f068a-9d98-454d-a682-5d657cfc798b" />


```


df['Age'].value_counts()

```

<img width="198" height="581" alt="Screenshot 2025-09-15 222048" src="https://github.com/user-attachments/assets/bce5a38f-9783-44ce-a228-41a41d14f46c" />


```


df.set_index("PassengerId",inplace=True)
df

```



<img width="1278" height="587" alt="Screenshot 2025-09-15 230445" src="https://github.com/user-attachments/assets/7ba7d163-ecc5-41f5-9407-305e4f227db5" />


```



df.nunique()


```



<img width="167" height="519" alt="Screenshot 2025-09-15 222157" src="https://github.com/user-attachments/assets/ae7e21cf-e378-4244-95b2-0532f4188b15" />


```



sns.countplot(data=df,x="Survived")



```



<img width="766" height="566" alt="Screenshot 2025-09-15 222314" src="https://github.com/user-attachments/assets/9825f47b-70b9-481e-b3d4-5983fbbf3c06" />



```




df.Pclass.unique()



```


<img width="200" height="41" alt="Screenshot 2025-09-15 224013" src="https://github.com/user-attachments/assets/00d7b31a-f674-42b8-8954-ada2151cd08d" />


```


df.rename(columns={'Sex':'Gender'},inplace=True)
df


```


<img width="1440" height="556" alt="Screenshot 2025-09-15 224150" src="https://github.com/user-attachments/assets/2e0a05ea-2e29-410f-baea-77837085159f" />


```


sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=0.7)



```


<img width="930" height="638" alt="Screenshot 2025-09-15 224315" src="https://github.com/user-attachments/assets/2542b362-b8c5-4a55-9d0d-aa6377a585d4" />


```


df.boxplot(coloumn="Age",by="Survived")


```


<img width="797" height="600" alt="Screenshot 2025-09-15 224419" src="https://github.com/user-attachments/assets/abe734eb-8f5a-46f9-b99a-b3ee659a1375" />



```


sns.scatterplot( x=df["Age"],y=df["Fare"])


```


<img width="787" height="575" alt="Screenshot 2025-09-15 224555" src="https://github.com/user-attachments/assets/59e7b6a3-3480-4120-9498-712954b816a1" />



```


#fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(x="Pclass",y="Age",hue="Gender",data=df)



```


<img width="775" height="539" alt="Screenshot 2025-09-15 224719" src="https://github.com/user-attachments/assets/3f41f892-684a-45b8-b4fb-a035138fac05" />



```


sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")


```


<img width="1379" height="641" alt="Screenshot 2025-09-15 224946" src="https://github.com/user-attachments/assets/d7ffd40f-53a2-4b32-bec0-51d2cbc9198b" />



```


numeric_df = df.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)


```


<img width="735" height="557" alt="Screenshot 2025-09-15 225132" src="https://github.com/user-attachments/assets/5cb086d3-655d-4a64-9b1e-e7d0d0295105" />








# RESULT
        
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
