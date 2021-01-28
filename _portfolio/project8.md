---
title: Project Name
subtitle: Lorem ipsum dolor sit amet consectetur.
image: https://raw.githubusercontent.com/BlackrockDigital/startbootstrap-agency/master/src/assets/img/portfolio/06-full.jpg
alt: 

caption:
  title: Linear
  subtitle: Photography
  thumbnail: assets/img/portfolio/monte1.jpg
---




```python
import numpy as np
import pandas as pd


import os
```


```python
data = pd.read_excel('C://Users//madi//Desktop//Data Set for Customers.xlsx')
data.head()
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
      <th>CustomerID</th>
      <th>Gender</th>
      <th>Age</th>
      <th>Annual Income (INR)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>Male</td>
      <td>19</td>
      <td>15</td>
      <td>39</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>Male</td>
      <td>21</td>
      <td>15</td>
      <td>81</td>
    </tr>
    <tr>
      <td>2</td>
      <td>3</td>
      <td>Female</td>
      <td>20</td>
      <td>16</td>
      <td>6</td>
    </tr>
    <tr>
      <td>3</td>
      <td>4</td>
      <td>Female</td>
      <td>23</td>
      <td>16</td>
      <td>77</td>
    </tr>
    <tr>
      <td>4</td>
      <td>5</td>
      <td>Female</td>
      <td>31</td>
      <td>17</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
</div>




```python
len(data)
```




    200




```python
data['Gender'].value_counts()
```




    Female    112
    Male       88
    Name: Gender, dtype: int64




```python
data.drop(['CustomerID'],axis =1).describe()
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
      <th>Age</th>
      <th>Annual Income (INR)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>200.000000</td>
      <td>200.000000</td>
      <td>200.000000</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>38.850000</td>
      <td>60.560000</td>
      <td>50.200000</td>
    </tr>
    <tr>
      <td>std</td>
      <td>13.969007</td>
      <td>26.264721</td>
      <td>25.823522</td>
    </tr>
    <tr>
      <td>min</td>
      <td>18.000000</td>
      <td>15.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>28.750000</td>
      <td>41.500000</td>
      <td>34.750000</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>36.000000</td>
      <td>61.500000</td>
      <td>50.000000</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>49.000000</td>
      <td>78.000000</td>
      <td>73.000000</td>
    </tr>
    <tr>
      <td>max</td>
      <td>70.000000</td>
      <td>137.000000</td>
      <td>99.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
data[data['Gender'] == "Male"].drop(['CustomerID'],axis =1).describe()
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
      <th>Age</th>
      <th>Annual Income (INR)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>88.000000</td>
      <td>88.000000</td>
      <td>88.000000</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>39.806818</td>
      <td>62.227273</td>
      <td>48.511364</td>
    </tr>
    <tr>
      <td>std</td>
      <td>15.514812</td>
      <td>26.638373</td>
      <td>27.896770</td>
    </tr>
    <tr>
      <td>min</td>
      <td>18.000000</td>
      <td>15.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>27.750000</td>
      <td>45.500000</td>
      <td>24.500000</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>37.000000</td>
      <td>62.500000</td>
      <td>50.000000</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>50.500000</td>
      <td>78.000000</td>
      <td>70.000000</td>
    </tr>
    <tr>
      <td>max</td>
      <td>70.000000</td>
      <td>137.000000</td>
      <td>97.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
data[data['Gender'] == "Female"].drop(['CustomerID'],axis =1).describe()
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
      <th>Age</th>
      <th>Annual Income (INR)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>112.000000</td>
      <td>112.000000</td>
      <td>112.000000</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>38.098214</td>
      <td>59.250000</td>
      <td>51.526786</td>
    </tr>
    <tr>
      <td>std</td>
      <td>12.644095</td>
      <td>26.011952</td>
      <td>24.114950</td>
    </tr>
    <tr>
      <td>min</td>
      <td>18.000000</td>
      <td>16.000000</td>
      <td>5.000000</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>29.000000</td>
      <td>39.750000</td>
      <td>35.000000</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>35.000000</td>
      <td>60.000000</td>
      <td>50.000000</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>47.500000</td>
      <td>77.250000</td>
      <td>73.000000</td>
    </tr>
    <tr>
      <td>max</td>
      <td>68.000000</td>
      <td>126.000000</td>
      <td>99.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
from matplotlib import pyplot as plt
%matplotlib inline
```


```python
# Approch 1 - Subplots

fig = plt.figure(figsize=(15,3)) 
# plt.rcParams['figure.figsize'] = 15,3]

plt.subplot(1, 3, 1)
plt.hist(data['Annual Income (INR)'])
plt.xlabel('Annual Income (INR)')

plt.subplot(1, 3, 2)
plt.hist(data['Age'])
plt.xlabel('Age')

plt.subplot(1, 3, 3)
plt.hist(data['Spending Score (1-100)'])
plt.xlabel('Spending Score (1-100)')

plt.show()
```


    
image:https://github.com/manisatya009/009/blob/master/assets/img/project8/output_8_0.png
    



```python
import seaborn as sns

g = sns.FacetGrid(data, col="Gender")
g.map(plt.scatter, "Age", "Spending Score (1-100)", alpha=.7)
g.add_legend()

## Age less than 40 people are spending more irrespective of Gender
```




    <seaborn.axisgrid.FacetGrid at 0x1cbb5c48548>




    
![009](/assets/img/project8.png)
    



```python
g = sns.FacetGrid(data, col="Gender")
g.map(plt.scatter, "Annual Income (INR)", "Spending Score (1-100)", alpha=.7)
g.add_legend()

## similar spending tends in M/F w.r.t income
## around a Income of 50 we see less variation in spending behaviour
```




    <seaborn.axisgrid.FacetGrid at 0x1cbb5cfb208>





    
![png](output_10_1.png)
    



```python
## CORRELATION
data.drop(['CustomerID'],axis =1).corr()

## Age is negetively correlated to spendings in this mall
## There is not much direct correlation b/w spending and income!!
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
      <th>Age</th>
      <th>Annual Income (INR)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Age</td>
      <td>1.000000</td>
      <td>-0.012398</td>
      <td>-0.327227</td>
    </tr>
    <tr>
      <td>Annual Income (INR)</td>
      <td>-0.012398</td>
      <td>1.000000</td>
      <td>0.009903</td>
    </tr>
    <tr>
      <td>Spending Score (1-100)</td>
      <td>-0.327227</td>
      <td>0.009903</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
top_spending_scores = data['Spending Score (1-100)'].sort_values(ascending=False)[:20]

## High Spending score individuals

tsi = data[data['Spending Score (1-100)'].isin(top_spending_scores.values)] # top spending individuals
tsi.head()
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
      <th>CustomerID</th>
      <th>Gender</th>
      <th>Age</th>
      <th>Annual Income (INR)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>7</td>
      <td>8</td>
      <td>Female</td>
      <td>23</td>
      <td>18</td>
      <td>94</td>
    </tr>
    <tr>
      <td>11</td>
      <td>12</td>
      <td>Female</td>
      <td>35</td>
      <td>19</td>
      <td>99</td>
    </tr>
    <tr>
      <td>19</td>
      <td>20</td>
      <td>Female</td>
      <td>35</td>
      <td>23</td>
      <td>98</td>
    </tr>
    <tr>
      <td>33</td>
      <td>34</td>
      <td>Male</td>
      <td>18</td>
      <td>33</td>
      <td>92</td>
    </tr>
    <tr>
      <td>41</td>
      <td>42</td>
      <td>Male</td>
      <td>24</td>
      <td>38</td>
      <td>92</td>
    </tr>
  </tbody>
</table>
</div>




```python
tsi.drop(['CustomerID'],axis =1).describe()

## All the top spenders are under 40
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
      <th>Age</th>
      <th>Annual Income (INR)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>31.750000</td>
      <td>69.350000</td>
      <td>92.600000</td>
    </tr>
    <tr>
      <td>std</td>
      <td>5.847852</td>
      <td>27.951603</td>
      <td>3.393492</td>
    </tr>
    <tr>
      <td>min</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>88.000000</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>28.750000</td>
      <td>61.250000</td>
      <td>90.000000</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>32.500000</td>
      <td>77.500000</td>
      <td>92.000000</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>35.250000</td>
      <td>86.250000</td>
      <td>95.000000</td>
    </tr>
    <tr>
      <td>max</td>
      <td>40.000000</td>
      <td>113.000000</td>
      <td>99.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
tsi['Gender'].value_counts() 
```




    Male      11
    Female     9
    Name: Gender, dtype: int64




```python
low_spending_scores = data['Spending Score (1-100)'].sort_values(ascending=True)[:20]

## High Spending score individuals

lsi = data[data['Spending Score (1-100)'].isin(low_spending_scores.values)] # top spending individuals
lsi.head()
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
      <th>CustomerID</th>
      <th>Gender</th>
      <th>Age</th>
      <th>Annual Income (INR)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2</td>
      <td>3</td>
      <td>Female</td>
      <td>20</td>
      <td>16</td>
      <td>6</td>
    </tr>
    <tr>
      <td>6</td>
      <td>7</td>
      <td>Female</td>
      <td>35</td>
      <td>18</td>
      <td>6</td>
    </tr>
    <tr>
      <td>8</td>
      <td>9</td>
      <td>Male</td>
      <td>64</td>
      <td>19</td>
      <td>3</td>
    </tr>
    <tr>
      <td>14</td>
      <td>15</td>
      <td>Male</td>
      <td>37</td>
      <td>20</td>
      <td>13</td>
    </tr>
    <tr>
      <td>22</td>
      <td>23</td>
      <td>Female</td>
      <td>46</td>
      <td>25</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
lsi.drop(['CustomerID'],axis =1).describe()
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
      <th>Age</th>
      <th>Annual Income (INR)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>21.000000</td>
      <td>21.000000</td>
      <td>21.000000</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>39.857143</td>
      <td>61.285714</td>
      <td>7.190476</td>
    </tr>
    <tr>
      <td>std</td>
      <td>14.301349</td>
      <td>29.351564</td>
      <td>3.842122</td>
    </tr>
    <tr>
      <td>min</td>
      <td>19.000000</td>
      <td>16.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>33.000000</td>
      <td>30.000000</td>
      <td>5.000000</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>37.000000</td>
      <td>73.000000</td>
      <td>6.000000</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>52.000000</td>
      <td>78.000000</td>
      <td>10.000000</td>
    </tr>
    <tr>
      <td>max</td>
      <td>64.000000</td>
      <td>113.000000</td>
      <td>13.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
lsi['Gender'].value_counts()  ## more males in Least spending individuals
```




    Male      15
    Female     6
    Name: Gender, dtype: int64




```python

```


```python

```
