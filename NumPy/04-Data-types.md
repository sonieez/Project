📍NumPy Data Types:

✔️By default Python have these data types:
1) `strings` - used to represent text data, the text is given under quote marks. e.g. "ABCD"
2) `integer` - used to represent integer numbers. e.g. -1, -2, -3
3) `float` - used to represent real numbers. e.g. 1.2, 42.42
4) `boolean` - used to represent True or False.
5) `complex` - used to represent complex numbers. e.g. 1.0 + 2.0j, 1.5 + 2.5j

✔️NumPy has some extra data types, and refer to data types with one character:
1) `i` - integer
2) `b` - boolean
3) `u` - unsigned integer
4) `f` - float
5) `c` - complex float
6) `m` - timedelta
7) `M` - datetime
8) `O` - object
9) `S` - string
10) `U` - unicode string
11) `V` - fixed chunk of memory for other type ( void )

✔️The NumPy array object has a property called `dtype` that returns the data type of the array:
```python
arr = np.array([1, 2, 3, 4])
print(arr.dtype)   #int64

arr = np.array(['apple', 'banana', 'cherry'])
print(arr.dtype)   #<U6
```
✔️We use the `array()` function to create arrays, this function can take an optional argument `dtype` that allows us to define the expected data type of the array elements:
```python
arr = np.array([1, 2, 3, 4], dtype='S')
```
✔️If a type is given in which elements can't be casted then NumPy will raise a ValueError:
```python
arr = np.array(['a', '2', '3'], dtype='i')
```
✔️Converting Data Type on Existing Arrays:

   The best way to change the data type of an existing array, is to make a copy of the array       with the `astype()` method.

   The `astype()` function creates a copy of the array, and allows you to specify the data type     as a parameter.

   The data type can be specified using a string, like `f` for float, `i` for integer etc. or       you can use the data type directly like float for float and int for integer.
```python
arr = np.array([1.1, 2.1, 3.1])
newarr = arr.astype('i')
#or
newarr = arr.astype(int)
```
