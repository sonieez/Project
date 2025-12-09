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
