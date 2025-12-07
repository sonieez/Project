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

