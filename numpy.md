py_list to np_array
`np.array(a_list)`

np_array to py_list
`np_array.tolist()`
___

creat a numpy array
```
>>> np.arange(3)
array([0, 1, 2])
>>> np.arange(3, step=0.1)
array([0. , 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1. , 1.1, 1.2,
       1.3, 1.4, 1.5, 1.6, 1.7, 1.8, 1.9, 2. , 2.1, 2.2, 2.3, 2.4, 2.5,
       2.6, 2.7, 2.8, 2.9])
>>> np.arange(1,3, step=0.5)
array([1. , 1.5, 2. , 2.5])
```
___

use np_array as list
```
for i in np_array:
   print(i)
```
___

get np_array index by value
```
index_list = np.where(np_array == some_value)[0]
print(index_list)
```

get np_array values  by index_list
```
value_list = np_array[index_list]
print(value_list)
```
___

Just remember, any list you put in numpy function, it will automatically converted to np_array.