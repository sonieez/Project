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
