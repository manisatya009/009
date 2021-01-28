---
title: Project Name
subtitle: Lorem ipsum dolor sit amet consectetur.
image: https://raw.githubusercontent.com/BlackrockDigital/startbootstrap-agency/master/src/assets/img/portfolio/06-full.jpg
alt: 

caption:
  title: Monte Carlo Simulation
  subtitle: Tool which is used to Predict uncertainity
  thumbnail: assets/img/portfolio/montecarlo.jpg
---
Use this area to describe your project. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Est blanditiis dolorem culpa incidunt minus dignissimos deserunt repellat aperiam quasi sunt officia expedita beatae cupiditate, maiores repudiandae, nostrum, reiciendis facere nemo!
Female    112
Male       88
Name: Gender, dtype: int64

data.drop(['CustomerID'],axis =1).describe()


 
1 Mg Mall
Last Checkpoint: 12/08/2020
(autosaved)
 
Logout 

Python 3  

Not Trusted
File
Edit
View
Insert
Cell
Kernel
Widgets
Help







Run






In [1]:


import numpy as np
import pandas as pd
​
​
import os



In [3]:


data = pd.read_excel('C://Users//madi//Desktop//Data Set for Customers.xlsx')
data.head()


Out[3]:

CustomerID
Gender
Age
Annual Income (INR)
Spending Score (1-100)
0
1
Male
19
15
39
1
2
Male
21
15
81
2
3
Female
20
16
6
3
4
Female
23
16
77
4
5
Female
31
17
40
In [4]:


len(data)


Out[4]:
200
In [5]:


data['Gender'].value_counts()


Out[5]:
Female    112
Male       88
Name: Gender, dtype: int64
In [6]:


data.drop(['CustomerID'],axis =1).describe()


Out[6]:

Age
Annual Income (INR)
Spending Score (1-100)
count
200.000000
200.000000
200.000000
mean
38.850000
60.560000
50.200000
std
13.969007
26.264721
25.823522
min
18.000000
15.000000
1.000000
25%
28.750000
41.500000
34.750000
50%
36.000000
61.500000
50.000000
75%
49.000000
78.000000
73.000000
max
70.000000
137.000000
99.000000
In [7]:


data[data['Gender'] == "Male"].drop(['CustomerID'],axis =1).describe()


Out[7]:

Age
Annual Income (INR)
Spending Score (1-100)
count
88.000000
88.000000
88.000000
mean
39.806818
62.227273
48.511364
std
15.514812
26.638373
27.896770
min
18.000000
15.000000
1.000000
25%
27.750000
45.500000
24.500000
50%
37.000000
62.500000
50.000000
75%
50.500000
78.000000
70.000000
max
70.000000
137.000000
97.000000
In [8]:


data[data['Gender'] == "Female"].drop(['CustomerID'],axis =1).describe()


Out[8]:

Age
Annual Income (INR)
Spending Score (1-100)
count
112.000000
112.000000
112.000000
mean
38.098214
59.250000
51.526786
std
12.644095
26.011952
24.114950
min
18.000000
16.000000
5.000000
25%
29.000000
39.750000
35.000000
50%
35.000000
60.000000
50.000000
75%
47.500000
77.250000
73.000000
max
68.000000
126.000000
99.000000
In [9]:


from matplotlib import pyplot as plt
%matplotlib inline



In [9]:


# Approch 1 - Subplots
​
fig = plt.figure(figsize=(15,3)) 
# plt.rcParams['figure.figsize'] = 15,3]
​
plt.subplot(1, 3, 1)
plt.hist(data['Annual Income (INR)'])
plt.xlabel('Annual Income (INR)')
​
plt.subplot(1, 3, 2)
plt.hist(data['Age'])
plt.xlabel('Age')
​
plt.subplot(1, 3, 3)
plt.hist(data['Spending Score (1-100)'])
plt.xlabel('Spending Score (1-100)')
​
plt.show()




In [13]:


import seaborn as sns
​
g = sns.FacetGrid(data, col="Gender")
g.map(plt.scatter, "Age", "Spending Score (1-100)", alpha=.7)
g.add_legend()
​
## Age less than 40 people are spending more irrespective of Gender


Out[13]:
<seaborn.axisgrid.FacetGrid at 0x1cbb5c48548>


In [14]:


g = sns.FacetGrid(data, col="Gender")
g.map(plt.scatter, "Annual Income (INR)", "Spending Score (1-100)", alpha=.7)
g.add_legend()
​
## similar spending tends in M/F w.r.t income
## around a Income of 50 we see less variation in spending behaviour


Out[14]:
<seaborn.axisgrid.FacetGrid at 0x1cbb5cfb208>


In [15]:


## CORRELATION
data.drop(['CustomerID'],axis =1).corr()
​
## Age is negetively correlated to spendings in this mall
## There is not much direct correlation b/w spending and income!!


Out[15]:

Age
Annual Income (INR)
Spending Score (1-100)
Age
1.000000
-0.012398
-0.327227
Annual Income (INR)
-0.012398
1.000000
0.009903
Spending Score (1-100)
-0.327227
0.009903
1.000000
In [16]:


top_spending_scores = data['Spending Score (1-100)'].sort_values(ascending=False)[:20]
​
## High Spending score individuals
​
tsi = data[data['Spending Score (1-100)'].isin(top_spending_scores.values)] # top spending individuals
tsi.head()


Out[16]:

CustomerID
Gender
Age
Annual Income (INR)
Spending Score (1-100)
7
8
Female
23
18
94
11
12
Female
35
19
99
19
20
Female
35
23
98
33
34
Male
18
33
92
41
42
Male
24
38
92
In [17]:


tsi.drop(['CustomerID'],axis =1).describe()
​
## All the top spenders are under 40


Out[17]:

Age
Annual Income (INR)
Spending Score (1-100)
count
20.000000
20.000000
20.000000
mean
31.750000
69.350000
92.600000
std
5.847852
27.951603
3.393492
min
18.000000
18.000000
88.000000
25%
28.750000
61.250000
90.000000
50%
32.500000
77.500000
92.000000
75%
35.250000
86.250000
95.000000
max
40.000000
113.000000
99.000000
In [18]:


tsi['Gender'].value_counts() 


Out[18]:
Male      11
Female     9
Name: Gender, dtype: int64
In [19]:


low_spending_scores = data['Spending Score (1-100)'].sort_values(ascending=True)[:20]
​
## High Spending score individuals
​
lsi = data[data['Spending Score (1-100)'].isin(low_spending_scores.values)] # top spending individuals
lsi.head()


Out[19]:

CustomerID
Gender
Age
Annual Income (INR)
Spending Score (1-100)
2
3
Female
20
16
6
6
7
Female
35
18
6
8
9
Male
64
19
3
14
15
Male
37
20
13
22
23
Female
46
25
5
In [20]:


lsi.drop(['CustomerID'],axis =1).describe()


Out[20]:

Age
Annual Income (INR)
Spending Score (1-100)
count
21.000000
21.000000
21.000000
mean
39.857143
61.285714
7.190476
std
14.301349
29.351564
3.842122
min
19.000000
16.000000
1.000000
25%
33.000000
30.000000
5.000000
50%
37.000000
73.000000
6.000000
75%
52.000000
78.000000
10.000000
max
64.000000
113.000000
13.000000
In [21]:


lsi['Gender'].value_counts()  ## more males in Least spending individuals


Out[21]:
Male      15
Female     6
Name: Gender, dtype: int64
In [ ]:


​



In [ ]:


​




{:.list-inline}
- Date: October 2019
- Client: Window
- Category: Photography

