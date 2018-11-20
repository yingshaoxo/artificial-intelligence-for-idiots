`Pandas` is a Python tool for handling `tables`, which works like excel, but it's programmable.

```
import pandas as pd
```
___

Create your first `DataFrame`

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

A general pandas `DataFrame`

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

get one column of your pandas dataframe

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

get two columns of your pandas dataframe

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

drop a column in the table

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