# Numpy

`Numpy` is a short name of `number of python`

> `numpy` is a python library for number processing.

```text
import numpy as np
```

py\_list to np\_array `np.array(a_list)`

np\_array to py\_list `np_array.tolist()`

creat a numpy array

```text
>>> np.arange(3)
array([0, 1, 2])
>>> np.arange(3, step=0.1)
array([0. , 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1. , 1.1, 1.2,
       1.3, 1.4, 1.5, 1.6, 1.7, 1.8, 1.9, 2. , 2.1, 2.2, 2.3, 2.4, 2.5,
       2.6, 2.7, 2.8, 2.9])
>>> np.arange(1,3, step=0.5)
array([1. , 1.5, 2. , 2.5])
```

use np\_array as list

```text
for i in np_array:
   print(i)
```

get np\_array index by value

```text
index_list = np.where(np_array == some_value)[0]
print(index_list)
```

get np\_array values by index\_list

```text
value_list = np_array[index_list]
print(value_list)
```

Just remember, any list you put in numpy function, it will automatically converted to np\_array.

