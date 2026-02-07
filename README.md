### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 07-02-2026
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("/clustervisitor.csv")

cluster = {
    "young": df['Age'] <= 30,
    "Middle": (df['Age'] > 30) & (df['Age'] < 50),
    "old": df['Age'] >= 50
}

for group, condition in cluster.items():
    visitors = df[condition]
    visitor_count = len(visitors)

    print(f"\nVisitors in {group} group:")
    print(visitors)
    print(f"Total visitors: {visitor_count}")

```
### Output:
<img width="351" height="685" alt="image" src="https://github.com/user-attachments/assets/29d1b08b-1e3c-4cfc-bc1f-c2c02151cc45" />

### Visualization:
```python
df['Income'] = df['Age'].apply(
    lambda x: 20000 + x*1200 if x <= 30 else 30000 + x*1800
)

from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans

df1 = df['Age']
df2 = df['Income']
df3 = pd.concat([df1,df2],axis=1)

s = StandardScaler()
new_df = s.fit_transform(df3)
mean = KMeans(n_clusters = 3, random_state=42)
df3['Cluster'] = mean.fit_predict(new_df)
df3
```
### Output:

<img width="285" height="619" alt="image" src="https://github.com/user-attachments/assets/37cfd4e3-e272-4f8c-b37c-646469201f36" />


### Result:
Cluster and Visitor Segmentation for Navigation patterns in Python has been successfully implemented.

