# Pandas

## First in first

`Pandas` is a Python tool for handling `tables`, which works like excel, but it's programmable.

```text
import pandas as pd
```

## Create your first `DataFrame`

```text
>>> numpy_array = np.arange(1,3, step=0.5)
>>> pd.DataFrame(numpy_array)
     0
0  1.0
1  1.5
2  2.0
3  2.5
```

## A general pandas `DataFrame`

```text
>>> data = {'column1': numpy_array, 'column2': numpy_array*2}
>>> pd.DataFrame(data)
   column1  column2
0      1.0      2.0
1      1.5      3.0
2      2.0      4.0
3      2.5      5.0
```

## get one column from your pandas dataframe

```text
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

## get two columns from your pandas dataframe

```text
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

## drop a column in your table

```text
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

> {0 or ‘index’, 1 or ‘columns’}, default 0 index is a number, columns is a string, for both values, you can put it into a list for batch handling

## get a new column based on other exists columns

```text
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

## add a column to your table

```text
>>> new_column = table.apply(lambda row: greater_than_2(row), axis=1)
>>> table['new_column'] = new_column
>>> table
   column1  column2 new_column
0      1.0      2.0         no
1      1.5      3.0         no
2      2.0      4.0         no
3      2.5      5.0        yes
```

## create an empty table with head titles

```python
>>> table = pd.DataFrame(columns=["name", "age"])
>>> table
Empty DataFrame
Columns: [name, age]
Index: []
```

## add a row to that table with a dict

```python
>>> new_row = {'name':'yingshaoxo', 'age':22}
>>> table = table.append(new_row, ignore_index=True)
>>> table
         name age
0  yingshaoxo  22
```

## add a row to that table with a list

```python
>>> new_row = ["yingshaoxo", 22]
>>> a_series = pd.Series(new_row, index=table.columns)
>>> table = table.append(a_series, ignore_index=True)
>>> table
         name age
0  yingshaoxo  22
1  yingshaoxo  22
```

## export your table as an excel file

```python
table.to_excel("hello.xlsx")
```

## read your excel table

```python
table = pd.read_excel('hello.xlsx', index_col=0)  
```

## get one column as a NumPy array

```python
>>> df = pd.DataFrame({"A":[1, 2], "B":[3, 4], "C":[5, 6]})
>>> df[["A"]].to_numpy()
array([[1],
       [2]], dtype=int64)
```

