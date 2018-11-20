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