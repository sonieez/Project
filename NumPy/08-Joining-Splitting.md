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
