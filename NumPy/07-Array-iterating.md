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
