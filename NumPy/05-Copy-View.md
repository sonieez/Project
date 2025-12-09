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
