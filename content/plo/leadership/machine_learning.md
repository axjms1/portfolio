---
title: "Machine Learning"
description: "Leadership - Artifact 4"
date: 2023-07-01
draft: false
tags: ["Leadership", "EDTECH 597", "Machine Learning", "Python", "Jupyter"]
weight: 40
---
I would be remiss not to include an artifact from my favorite course in the program.  Introduction to Machine Learning Education (EDTECH 597) provided an excellent introduction to machine learning and data analysis using [Python](https://www.python.org/), [Orange](https://orangedatamining.com/), and [Jupyter Notebooks](https://jupyter.org/). The artifact linked below is from an exercise later in the course where various machine learning models were applied to a dataset and evaluated.  Further below is a representative output from a Jupyter notebook used in the course.  Machine learning is one of the most interesting applications of artificial intelligence (AI) in education with the recent exception of generative AI and large language models (LLMs).

The lessons provided from this course provided a springboard from which I was able to extend my knowledge of python and data analysis and pursue an entirely different career.  I use these tools on a daily basis as a test engineer.

**[Selected Machine Learning Assignment](https://docs.google.com/document/d/1K5ktqn4yM1y8mTt4gl82wZ7HsOacJfvV/preview)**
____

```python
#import necessary packages
import pandas as pd #import pandas 
from sklearn.cluster import KMeans #import kmeans 
import matplotlib.pyplot as plt #import matplotlib for data visualization
import warnings #ignore general warnings
warnings.filterwarnings("ignore")
```


```python
df = pd.read_csv('log_processed.csv') #import processed data
```


```python
#group students based on their learning behaviors. Therefore, keep learning behavior related variables
df1=df[['content_access', 'assessment_access', 'interaction_frequency', 'check_grade', 'others']] 
```


```python
df1 #print df1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>content_access</th>
      <th>assessment_access</th>
      <th>interaction_frequency</th>
      <th>check_grade</th>
      <th>others</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>247.0</td>
      <td>144.0</td>
      <td>69.0</td>
      <td>75.0</td>
      <td>20.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>797.0</td>
      <td>209.0</td>
      <td>146.0</td>
      <td>141.0</td>
      <td>139.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>455.0</td>
      <td>1067.0</td>
      <td>193.0</td>
      <td>119.0</td>
      <td>32.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>745.0</td>
      <td>173.0</td>
      <td>99.0</td>
      <td>176.0</td>
      <td>50.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>473.0</td>
      <td>167.0</td>
      <td>49.0</td>
      <td>152.0</td>
      <td>55.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>6743</th>
      <td>0.0</td>
      <td>20.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>6744</th>
      <td>2.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>6745</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>6746</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>6747</th>
      <td>0.0</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>6748 rows × 5 columns</p>
</div>




```python
ks = range(1,10) #test clustering from 1 9 clusters 1-9
inertias = []
for k in ks:
    model = KMeans(n_clusters=k) 
    model.fit(df1) # put your dataset here for running the clustering analysis
    inertias.append(model.inertia_) #append inertia_value to the list. 
    #The value is the squared sum of distance between individual points with its cluster's centroid. 
    #Smaller value => lower squared sum of distance with individual clusters. 

plt.figure(figsize=(10,8)) #Figure size
plt.plot(ks,inertias,'-o',color='g') # x, y,style,color
plt.xlabel('number of clusters, k',size=15) #x label
plt.ylabel('inertia',size=15) #y label
plt.xticks(ks) # ticks on the X axis
plt.show() #Plot
```
    



```python

```
{{< paige/image src="./plo/leadership/K-Means_Clusters_4_0.png" alt="K-Means Clusters Plot" >}}