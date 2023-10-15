# Ex:05 Feature Generation

## AIM:
To read the given data and perform Feature Generation process and save the data to a file.

## Explanation:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

## ALGORITHM:
STEP 1
Read the given Data.

STEP 2
Clean the Data Set using Data Cleaning Process.

STEP 3
Apply Feature Generation techniques to all the feature of the data set.

STEP 4
Save the data to the file.

## CODE:
```
Developed by : DELLI PRIYA L         
Reg No : 212222230029
```
### Data.csv:
```
import pandas as pd
df=pd.read_csv("data.csv")
print(df)

import category_encoders as ce
be=ce.BinaryEncoder()
df1=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
df1

be=ce.BinaryEncoder()
df2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
df2

df1=df.copy()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
import category_encoders as ce
be=ce.BinaryEncoder()
ohe=OneHotEncoder(sparse=False)
le=LabelEncoder()
oe=OrdinalEncoder()

df1["City"] = ohe.fit_transform(df1[["City"]])
temp=['Cold','Warm','Hot','Very Hot']
oe1=OrdinalEncoder(categories=[temp])
df1['Ord_1'] = oe1.fit_transform(df1[["Ord_1"]])
edu=['High School','Diploma','Bachelors','Masters','PhD']
oe2=OrdinalEncoder(categories=[edu])
df1['Ord_2']= oe2.fit_transform(df1[["Ord_2"]])
df1
```
### SCALING:
```
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=(['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target']))
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df5
```
### Encoding data:
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df
```
### GENERATION:
```
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

be=ce.BinaryEncoder()
ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
le=LabelEncoder()
oe=OrdinalEncoder()

df1["nom_0"] = oe.fit_transform(df1[["nom_0"]])
temp=['Cold','Warm','Hot']
oe2=OrdinalEncoder(categories=[temp])
df1['ord_2'] = oe2.fit_transform(df1[['ord_2']])
df1
```
### SCALING:
```
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df0=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df0

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df2=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df2

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df3=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df3

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df4=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df4
```

## OUTPUT :

### (i) Data.csv
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/35e20e38-01e3-4aef-a357-a4aef08dd6ac)
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/8738b981-537a-47a7-85ed-e04fe8d7f766)
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/eab152b8-beff-4ba4-a38d-0eab0dc1e796)
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/cf44ed12-b287-468b-872c-6fe41f8b25f3)
### Minmax scaling:
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/4fe857a5-d5a0-419a-8b19-31d9a718ca05)
### Standard scaling:
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/24c71ae7-fbaf-4435-94af-636fcaeb8f1f)
### Maxabs scaling:
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/c715a6d1-d0b3-41de-b34f-2163e0a67fdf)
### Robust scaling:
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/262a81a2-a3fd-435c-9aeb-bb02c10fabd3)
### (ii) Encoding data.csv
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/f7bc8758-2efc-42a2-8b41-d280d4d85ac0)
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/679cd812-8c46-4250-80af-f69a507386d2)
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/8327462a-3921-43dd-ba05-20a7dd600db9)
### Minmax scaler:
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/1b0211be-54ea-42f8-bfbb-654a40ab1368)
### Standard scaler:
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/7636eab4-6623-4fdc-bf5c-90407d18a066)
### Maxabs scaler:
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/50c39959-989c-4a55-a9ef-1fbc2a086b97)
### Robust scaler:
![image](https://github.com/Priya-Loganathan/ODD2023-Datascience-Ex-05/assets/121166075/585b8500-ffd0-46b8-8b10-3c3f084d159a)

## Result:
Thus the Feature Generation and Feature Scaling process is applied to the given data set.

