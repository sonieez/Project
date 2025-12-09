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
