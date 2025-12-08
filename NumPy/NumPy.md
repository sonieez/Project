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
