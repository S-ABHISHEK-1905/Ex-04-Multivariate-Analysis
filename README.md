# Ex-04-Multivariate-Analysis
##AIM:
To apply multivariate analysis on a give data set.
##Algorithm:

1.start

2.read the dta from the file

3.clean the data a)remove outliers b)fill the null value or drop the column

4.perform multivariate analysis a)scatter plot b)box plot c)heat map

Program: read and cleaned the null value
##code:
```
import pandas as pd

df=pd.read_csv("/content/SuperStore.csv")

df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])

df.isnull().sum()
```
![image](https://user-images.githubusercontent.com/66360846/195591398-43b43c17-26e0-468b-93d9-d5584f881f39.png)
![image](https://user-images.githubusercontent.com/66360846/195591440-4aa12201-70a5-4862-84a9-0bf100ff5aaf.png)
##scatter plot:
df.dtype
![image](https://user-images.githubusercontent.com/66360846/195591598-3d6d6c17-fb0c-45d9-882c-3b8a0755b562.png)
##kurtosis:
df.kurtosis()
![image](https://user-images.githubusercontent.com/66360846/195591694-29fa23a2-d864-4772-8c96-b56b578195bd.png)
##scatter plot:
import pandas as pd

import seaborn as sns

sns.boxplot(df['Sales'],df['Postal Code'])
![image](https://user-images.githubusercontent.com/66360846/195592019-97fb4bdb-e93d-4850-959b-cbda97c75310.png)
##Bar plot:
sns.barplot(x=df["Sales"],y=df["Postal Code"],data=df)
![image](https://user-images.githubusercontent.com/66360846/195592137-e517e11f-a301-4681-bed8-d3e3c8793df8.png)
##bar plot
import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

states=df.loc[:,["Postal Code","Sales"]]

states=states.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Postal Code")

plt.ylabel=("Sales")

plt.show()
![image](https://user-images.githubusercontent.com/66360846/195592224-f816adec-32ae-4d39-88f6-b299a6b4f54c.png)

import pandas as pd

import seaborn as sns import matplotlib.pyplot as plt

states=df.loc[:,["State","Postal Code"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Postal Code",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Sales")

plt.ylabel=("Postal Code")

plt.show()
![image](https://user-images.githubusercontent.com/66360846/195592304-51800aab-5497-45f5-a12e-feea651bb258.png)

##corr:

df.corr()
![image](https://user-images.githubusercontent.com/66360846/195592384-8da005d9-f708-4ae3-8471-91fa626831ee.png)

##Heatmap:

import numpy as np

import seaborn as sn

import matplotlib.pyplot as plt

data=pd.read_csv("/content/SuperStore.csv")

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sn.heatmap(data = data)

plt.show()
![image](https://user-images.githubusercontent.com/66360846/195592533-13147a8c-e97f-4a37-b4a3-b69fcd137025.png)
![image](https://user-images.githubusercontent.com/66360846/195592575-5515443a-b2c6-41b6-888b-bfa0c99ff8dc.png)
##RESULT:

Thus we have applied the multiivariate analysis sucessfully
