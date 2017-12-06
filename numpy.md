list to np_array
`np.array(a_list)`

np_array to list
`np_array.tolist()`

use np_array as list
```
for i in np_array:
   print(i)
```

get np_array index by value
```
index_list = np.where(np_array == some_value)[0]
print(index_list)
```

get np_array values  by index_list
```
print(np_array[index_list])
```

Just remember, any list you put in numpy function, it will automatically converted to np_array.