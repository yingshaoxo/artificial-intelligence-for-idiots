```
import numpy as np
import pandas as pd
```
___

#### First, let us get some intuition from it

```
>>> data_table = pd.read_csv("/home/yingshaoxo/500_Person_Gender_Height_Weight_Index.csv")

>>> data_table.head()
   Gender  Height  Weight  Index
0    Male     174      96      4
1    Male     189      87      2
2  Female     185     110      4
3  Female     195     104      3
4    Male     149      61      3
```
___

#### For our case, we only need the `height and weight` as `input`, `gender` as `output`

```
>>> x = data_table[['Height', 'Weight']].values
>>> x[:10]
array([[174,  96],
       [189,  87],
       [185, 110],
       [195, 104],
       [149,  61],
       [189, 104],
       [147,  92],
       [154, 111],
       [174,  90],
       [169, 103]])
```

```
>>> def convert_gender_to_number(row):
...     if row['Gender'] == 'Male':
...         return 1
...     else:
...         return 0
... 
>>> y = data_table[['Gender']].apply(lambda row: convert_gender_to_number(row), axis=1)
>>> y[:10]
0    1
1    1
2    0
3    0
4    1
5    1
6    1
7    1
8    1
9    0
```