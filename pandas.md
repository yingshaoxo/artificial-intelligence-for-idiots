#### First in first

`Pandas` is a Python tool for handling `tables`, which works like excel, but it's programmable.

```
import pandas as pd
```
___

#### Create your first `DataFrame`

```
>>> numpy_array = np.arange(1,3, step=0.5)
>>> pd.DataFrame(numpy_array)
     0
0  1.0
1  1.5
2  2.0
3  2.5
```
___

#### A general pandas `DataFrame`

```
>>> data = {'column1': numpy_array, 'column2': numpy_array*2}
>>> pd.DataFrame(data)
   column1  column2
0      1.0      2.0
1      1.5      3.0
2      2.0      4.0
3      2.5      5.0
```
___

#### get one column from your pandas dataframe

```
>>> table = pd.DataFrame(data)
>>> table
   column1  column2
0      1.0      2.0
1      1.5      3.0
2      2.0      4.0
3      2.5      5.0
>>> table['column1']
0    1.0
1    1.5
2    2.0
3    2.5
```
___

#### get two columns from your pandas dataframe

```
>>> data = {'column1': numpy_array, 'column2': numpy_array*2, 'another_column': numpy_array*3}
>>> table = pd.DataFrame(data)
>>> table
   column1  column2  another_column
0      1.0      2.0             3.0
1      1.5      3.0             4.5
2      2.0      4.0             6.0
3      2.5      5.0             7.5

>>> table[["column2", "another_column"]]
   column2  another_column
0      2.0             3.0
1      3.0             4.5
2      4.0             6.0
3      5.0             7.5

```
___

#### drop a column in your table

```
>>> table
   column1  column2  another_column
0      1.0      2.0             3.0
1      1.5      3.0             4.5
2      2.0      4.0             6.0
3      2.5      5.0             7.5

>>> table.drop("another_column", axis=1)
   column1  column2
0      1.0      2.0
1      1.5      3.0
2      2.0      4.0
3      2.5      5.0
```

Here the `axis` means: 
> {0 or ‘index’, 1 or ‘columns’}, default 0
> index is a number, columns is a string, for both values, you can put it into a list for batch handling

___

#### get a new column based on other exists columns

```
>>> table = table.drop("another_column", axis=1)
>>> table
   column1  column2
0      1.0      2.0
1      1.5      3.0
2      2.0      4.0
3      2.5      5.0

>>> def greater_than_2(row):
...     if row['column1'] > 2:
...         return 'yes'
...     else:
...         return 'no'
... 
>>> table.apply(lambda row: greater_than_2(row), axis=1)
0     no
1     no
2     no
3    yes
dtype: object
>>> 
```