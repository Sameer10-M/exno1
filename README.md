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
import numpy as np
import pandas as pd
data=pd.read_csv("SAMPLEIDS.csv")
data
```
<img width="943" height="718" alt="image" src="https://github.com/user-attachments/assets/ddd68e0d-aaaf-4887-9c17-2424923fd4cc" />

```
data.head(4)
```

<img width="1061" height="221" alt="image" src="https://github.com/user-attachments/assets/a84fc0d2-c5d7-4351-9e20-28a987c61f62" />

```
data.tail(7)
```
<img width="967" height="286" alt="image" src="https://github.com/user-attachments/assets/9c748578-4cbe-49f4-bc69-967f5e5e1cff" />

```
data.isnull()
```
<img width="828" height="674" alt="image" src="https://github.com/user-attachments/assets/1222cb6e-64d6-4c0b-8bff-fc2f082e4f2b" />

```
data.notnull()
```
<img width="932" height="682" alt="image" src="https://github.com/user-attachments/assets/cba38611-3c6b-491c-8834-fbdda97fc43f" />

```
data.isnull().sum()
```
<img width="430" height="302" alt="image" src="https://github.com/user-attachments/assets/87ad844d-8cfe-4402-a8f5-88e35142cf98" />

```
data.isnull().any()
```
<img width="351" height="282" alt="image" src="https://github.com/user-attachments/assets/612f4be3-ded7-475d-aaac-9c5b54b9cbea" />

```
data.dropna(axis=1)
```
<img width="467" height="681" alt="image" src="https://github.com/user-attachments/assets/0e549cec-9e61-419b-abf0-837d93488536" />

```
data.dropna(axis=0)
```
<img width="980" height="453" alt="image" src="https://github.com/user-attachments/assets/e3ec6719-d211-4b08-98fe-38b99f4eebeb" />

```
data.fillna(0)
```
<img width="931" height="421" alt="image" src="https://github.com/user-attachments/assets/2ec01727-2f76-4c38-b365-267e39ac7441" />

```
 data.fillna(method="ffill")
```
<img width="1133" height="672" alt="image" src="https://github.com/user-attachments/assets/479bd828-c56e-4654-9f23-f75333c72922" />

```
data.bfill()
```
<img width="994" height="677" alt="image" src="https://github.com/user-attachments/assets/9b437a25-14d0-4520-b5fe-7dea2e2fc177" />

```
 data.fillna({'REGNO':0, 'NAME':'PRAVEEN'})
```
<img width="928" height="692" alt="image" src="https://github.com/user-attachments/assets/513bd661-7b96-4062-8c07-eec1c75e1d43" />

```
 ir=pd.read_csv("iris.csv")
 ir
```
<img width="964" height="679" alt="image" src="https://github.com/user-attachments/assets/28aedcce-b40c-4dee-a0b7-17aa609cb4fb" />

```
ir.describe()
```
<img width="549" height="283" alt="image" src="https://github.com/user-attachments/assets/8549bf2f-5c1a-4b6f-b6ac-a75e4cfb06eb" />

```
 import seaborn as sns
 sns.boxplot(x="sepal_width",data=ir)
```
<img width="849" height="583" alt="image" src="https://github.com/user-attachments/assets/eceeac50-8574-4b21-be54-31bdfd677724" />

```
 q1=ir.sepal_width.quantile(0.25)
 q3=ir.sepal_width.quantile(0.75)
 iqr=q3-q1
 print(iqr)
```
<img width="494" height="125" alt="image" src="https://github.com/user-attachments/assets/2741d0b6-f6dd-4910-8b93-8fdbebf5f58b" />

```
 rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```
<img width="810" height="166" alt="image" src="https://github.com/user-attachments/assets/68078b74-6f3a-4ae4-8694-02f7d343fb18" />

```
rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid
```
<img width="821" height="444" alt="image" src="https://github.com/user-attachments/assets/814864ea-8ba3-4493-b886-94617dfc9f97" />

```
rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```
<img width="731" height="299" alt="image" src="https://github.com/user-attachments/assets/c9a4b97e-721b-4971-9594-893d68cda339" />

```
 import numpy as np
 import scipy.stats as stats
 z=np.abs(stats.zscore(ir.sepal_width))
 z
```
<img width="584" height="335" alt="image" src="https://github.com/user-attachments/assets/be6a11d1-72cb-4eb5-a01e-78413acc78d5" />

# Result
Thus the programs are executed successfully

