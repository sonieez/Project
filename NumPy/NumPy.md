✔️NumPy is a Python library used for working with arrays.

✔️It also has functions for working in domain of linear algebra, fourier transform, and matrices.

✔️NumPy was created in 2005 by Travis Oliphant. It is an open source project and you can use it freely.

✔️NumPy stands for Numerical Python.

✔️NumPy is usually imported under the `np` alias.
<hr>

📍NumPy Creating Arrays:

✔️NumPy is used to work with arrays. The array object in NumPy is called `ndarray`. 
We can create a NumPy `ndarray` object by using the `array()` function.

✔️To create an `ndarray`, we can pass a list, tuple or any array-like object into the
`array()` method, and it will be converted into an `ndarray`:
```python
import numpy as np

arr1 = np.array([1, 2, 3, 4, 5])
arr2 = np.array((1, 2, 3, 4, 5))
```
<hr>
📍Dimensions in Arrays:

✔️A dimension in arrays is one level of array depth (nested arrays).

1) 0-D Arrays:
   ```python
   arr = np.array(42)
   ```
   0-D arrays, or Scalars, are the elements in an array. Each value in an array is a 0-D array.
2) 1-D Arrays:
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   ```
   An array that has 0-D arrays as its elements is called uni-dimensional or 1-D array.
   These are the most common and basic arrays.
3) 2-D Arrays:
   ```python
   arr = np.array([[1, 2, 3], [4, 5, 6]])
   ```
   An array that has 1-D arrays as its elements is called a 2-D array. These are often used to     represent matrix or 2nd order tensors.
4) 3-D arrays:
   ```python
   arr = np.array([[[1, 2, 3], [4, 5, 6]], [[1, 2, 3], [4, 5, 6]]])
   ```
   An array that has 2-D arrays (matrices) as its elements is called 3-D array. These are often     used to represent a 3rd order tensor.

✔️NumPy Arrays provides the `ndim` attribute that returns an integer that tells us how many dimensions the array have.

✔️An array can have any number of dimensions.
When the array is created, you can define the number of dimensions by using the `ndmin` argument.
<hr>

📍Access Array Elements:

✔️Array indexing is the same as accessing an array element.
You can access an array element by referring to its index number.

✔️The indexes in NumPy arrays start with 0, meaning that the first element has index 0, and the second has index 1 etc.
```python

```
✔️To access elements from 2-D arrays we can use comma separated integers representing the dimension and the index of the element:
```python
arr = np.array([[1,2,3,4,5], [6,7,8,9,10]])
print('2nd element on 1st row: ', arr[0, 1])  #2
```
✔️To access elements from 3-D arrays we can use comma separated integers representing the dimensions and the index of the element:
```python
arr = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])
print(arr[0, 1, 2])
#third element of the second array of the first array -- 6
```
✔️Negative Indexing - Use negative indexing to access an array from the end:
```python
arr = np.array([[1,2,3,4,5], [6,7,8,9,10]])
print('Last element from 2nd dim: ', arr[1, -1])    #10
```
<hr>

📍NumPy Array Slicing:

✔️Slicing in python means taking elements from one given index to another given index.

✔️We pass slice instead of index like this: `[start:end]`.

✔️We can also define the step, like this: `[start:end:step]`.

✔️If we don't pass start its considered 0

✔️If we don't pass end its considered length of array in that dimension

✔️If we don't pass step its considered 1

✔️The result includes the start index, but excludes the end index.

```python
arr = np.array([1, 2, 3, 4, 5, 6, 7])

print(arr[1:5])  #[2 3 4 5]
print(arr[4:])  #[5 6 7]
print(arr[:4])  #[1 2 3 4]

print(arr[1:5:2])  #[2 4]
print(arr[::2])  #[1 3 5 7]
```
✔️Negative Slicing - Use the minus operator to refer to an index from the end:
```python
arr = np.array([1, 2, 3, 4, 5, 6, 7])
print(arr[-3:-1])  #[5 6] 
```
✔️Slicing 2-D Arrays: `[element:index]`
```python
arr = np.array([[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]])

print(arr[1, 1:4])  #[7 8 9]
print(arr[0:2, 2])  #from both elements --> index 2 -- [3 8]
print(arr[0:2, 1:4])  #from both elemnts --> slicing [1:4] -- [2 3 4] [7 8 9]
```
<hr>

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
<hr>

📍NumPy Array Copy vs View:

✔️The main difference between a copy and a view of an array is that the copy is a new array, and the view is just a view of the original array.

✔️The copy owns the data and any changes made to the copy will not affect original array, and any changes made to the original array will not affect the copy.

✔️The view does not own the data and any changes made to the view will affect the original array, and any changes made to the original array will affect the view.
```python
arr = np.array([1, 2, 3, 4, 5])
x = arr.copy()
arr[0] = 42
#arr = [42 2 3 4 5]
#x = [1 2 3 4 5]

arr = np.array([1, 2, 3, 4, 5])
x = arr.view()
arr[0] = 42
#arr = [42 2 3 4 5]
#x = [42 2 3 4 5]

arr = np.array([1, 2, 3, 4, 5])
x = arr.view()
x[0] = 42
#arr = [42 2 3 4 5]
#x = [42 2 3 4 5]
```
✔️Every NumPy array has the attribute `base` that returns `None` if the array owns the data.
Otherwise, the `base` attribute refers to the original object:
```python
np.array([1, 2, 3, 4, 5])

x = arr.copy()
y = arr.view()

print(x.base)   #None
print(y.base)   #[1 2 3 4 5]
```
✔️The `copy` returns `None`.

✔️The `view` returns the original array.
<hr>

📍NumPy Array Shape:

✔️The shape of an array is the number of elements in each dimension.

✔️NumPy arrays have an attribute called `shape` that returns a tuple with each index having the number of corresponding elements:
```python
arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])
print(arr.shape)    #(2, 4)
```
<hr>

📍NumPy Array Reshaping:

✔️Reshaping means changing the shape of an array.

✔️The shape of an array is the number of elements in each dimension.

✔️By reshaping we can add or remove dimensions or change number of elements in each dimension.

```python
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12])
#From 1-D

newarr = arr.reshape(4, 3) #to 2-D 
newarr = arr.reshape(2, 3, 2)  #to 3-D
```
✔️Unknown Dimension - You are allowed to have one "unknown" dimension. Meaning that you do not have to specify an exact number for one of the dimensions in the reshape method.

✔️Pass -1 as the value, and NumPy will calculate this number for you. (We can not pass -1 to more than one dimension.) 
```python
newarr = arr.reshape(2, 2, -1)
```
✔️Flattening array means converting a multidimensional array into a 1D array.
We can use `reshape(-1)` to do this.
```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
newarr = arr.reshape(-1)   #[1 2 3 4 5 6]
```
<hr>

📍NumPy Array Iterating:

✔️Iterating means going through elements one by one.

✔️As we deal with multi-dimensional arrays in numpy, we can do this using basic `for` loop of python.

✔️If we iterate on a n-D array it will go through n-1th dimension one by one.

✔️For printing every element in the dimension with `for` loop:
```python
#1-D
arr = np.array([1, 2, 3])
for x in arr:
  print(x)

#2-D
arr = np.array([[1, 2, 3], [4, 5, 6]])
for x in arr:
  for y in x:
    print(y)

#3-D
arr = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])
for x in arr:
  for y in x:
    for z in y:
      print(z)
```
✔️The function `nditer()` is a helping function that can be used from very basic to very advanced iterations.

✔️For printing every element in the dimension with `nditer()` :
```python
arr = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
for x in np.nditer(arr):
  print(x)
```
✔️We can use `op_dtypes` argument and pass it the expected datatype to change the datatype of elements while iterating.

✔️NumPy does not change the data type of the element in-place (where the element is in array) so it needs some other space to perform this action, that extra space is called buffer, and in order to enable it in `nditer()` we pass `flags=['buffered']`:
```python
arr = np.array([1, 2, 3])
for x in np.nditer(arr, flags=['buffered'], op_dtypes=['S']):
  print(x)
#printed:
#b'1'
#b'2'
#b'3'
```
✔️Enumeration means mentioning sequence number of somethings one by one. Sometimes we require corresponding index of the element while iterating, the `ndenumerate()` method can be used for those usecases:
```python
arr = np.array([1, 2, 3])
for idx, x in np.ndenumerate(arr):
  print(idx, x)
#printed:
#(0,) 1
#(1,) 2
#(2,) 3
```
<hr>

📍NumPy Joining Array:

✔️Joining means putting contents of two or more arrays in a single array.

✔️We pass a sequence of arrays that we want to join to the `concatenate()` function, along with the axis. If axis is not explicitly passed, it is taken as 0:
```python
#axis=0 --> 1-D
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
arr = np.concatenate((arr1, arr2))
#[1 2 3 4 5]

#axis=1 --> 2-D
arr1 = np.array([[1, 2], [3, 4]])
arr2 = np.array([[5, 6], [7, 8]])
arr = np.concatenate((arr1, arr2), axis=1)
#[[1 2 5 6]
#[3 4 7 8]]
```
✔️Stacking is same as concatenation, the only difference is that stacking is done along a new axis.

✔️We pass a sequence of arrays that we want to join to the `stack()` method along with the axis. If axis is not explicitly passed it is taken as 0.
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
arr = np.stack((arr1, arr2), axis=1)
#[[1 4]
#[2 5]
#[3 6]]
```
✔️NumPy provides a helper function: `hstack()` to stack along rows:
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
arr = np.hstack((arr1, arr2))
#[1 2 3 4 5 6]
```
✔️NumPy provides a helper function: `vstack()`  to stack along columns:
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
arr = np.vstack((arr1, arr2))
#[[1 2 3]
#[4 5 6]]
```
✔️NumPy provides a helper function: `dstack()` to stack along height, which is the same as depth:
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
arr = np.dstack((arr1, arr2))
#[[[1 4]
# [2 5]
# [3 6]]]
```
<hr>

📍NumPy Splitting Array:

✔️Joining merges multiple arrays into one and Splitting breaks one array into multiple.

✔️We use `array_split()` for splitting arrays, we pass it the array we want to split and the number of splits:
```pyhton
arr = np.array([1, 2, 3, 4, 5, 6])
newarr = np.array_split(arr, 3)
#[array([1, 2]), array([3, 4]), array([5, 6])]
```
✔️The return value of the `array_split()` method is a list containing each of the split as an array.

✔️In addition, you can specify which axis you want to do the split around(they are split along the column):
```python
arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12], [13, 14, 15], [16, 17, 18]])
newarr = np.array_split(arr, 3, axis=1)
```
✔️An alternate solution is using `hsplit()` opposite of `hstack()`.
<hr>

📍NumPy Searching Arrays:

✔️You can search an array for a certain value, and return the indexes that get a match.
To search an array, use the `where()` method:
```python
arr = np.array([1, 2, 3, 4, 5, 4, 4])
x = np.where(arr == 4)
#(array([3, 5, 6]),)
```
✔️There is a method called `searchsorted()` which performs a binary search in the array, and returns the index where the specified value would be inserted to maintain the search order:
```python
arr = np.array([6, 7, 8, 9])
x = np.searchsorted(arr, 7)
#1
```
✔️By default the left most index is returned, but we can give `side='right'` to return the right most index instead:
```python
arr = np.array([6, 7, 8, 9])
x = np.searchsorted(arr, 7, side='right')
#2
```
✔️To search for more than one value, use an array with the specified values:
```python
arr = np.array([1, 3, 5, 7])
x = np.searchsorted(arr, [2, 4, 6])
#[1 2 3]
```
<hr>

📍NumPy Sorting Arrays:

✔️Sorting means putting elements in an ordered sequence.

✔️Ordered sequence is any sequence that has an order corresponding to elements, like numeric or alphabetical, ascending or descending.

✔️The NumPy ndarray object has a function called `sort()`, that will sort a specified array.
```python
arr = np.array([3, 2, 0, 1])
print(np.sort(arr))
#[0 1 2 3]
```
❗This method returns a copy of the array, leaving the original array unchanged.
<hr>

📍NumPy Filter Array:

✔️Getting some elements out of an existing array and creating a new array out of them is called filtering.

✔️In NumPy, you filter an array using a boolean index list(a list of booleans corresponding to indexes in the array).

✔️If the value at an index is `True` that element is contained in the filtered array, if the value at that index is `False` that element is excluded from the filtered array.
```python
arr = np.array([41, 42, 43, 44])
x = [True, False, True, False]
newarr = arr[x]
#[41 43]
```

✔️We can filter an array like this:
```python
#Creating new list to filter array
arr = np.array([1, 2, 3, 4, 5, 6, 7])

filter_arr = []

for element in arr:
  if element % 2 == 0:
    filter_arr.append(True)
  else:
    filter_arr.append(False)

newarr = arr[filter_arr]
```
But NumPy provides a better way to write this:
```python
#Creating filter directly from array
arr = np.array([1, 2, 3, 4, 5, 6, 7])

filter_arr = arr % 2 == 0

newarr = arr[filter_arr]
```
