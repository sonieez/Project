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
