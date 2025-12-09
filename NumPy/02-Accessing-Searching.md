📍Access Array Elements:

✔️Array indexing is the same as accessing an array element.
You can access an array element by referring to its index number.

✔️The indexes in NumPy arrays start with 0, meaning that the first element has index 0, and the second has index 1 etc.
```python
arr = np.array([1, 2, 3, 4])
print(arr[0])     #1
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
