📍NumPy Array Shape:

✔️The shape of an array is the number of elements in each dimension.

✔️NumPy arrays have an attribute called `shape` that returns a tuple with each index having the number of corresponding elements:
```python
arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])
print(arr.shape)    #(2, 4)
```
<hr>

📍NumPy Array Reshaping:

✔️Reshaping means changing the shape of an array.

✔️The shape of an array is the number of elements in each dimension.

✔️By reshaping we can add or remove dimensions or change number of elements in each dimension.

```python
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12])
#From 1-D

newarr = arr.reshape(4, 3) #to 2-D 
newarr = arr.reshape(2, 3, 2)  #to 3-D
```
✔️Unknown Dimension - You are allowed to have one "unknown" dimension. Meaning that you do not have to specify an exact number for one of the dimensions in the reshape method.

✔️Pass -1 as the value, and NumPy will calculate this number for you. (We can not pass -1 to more than one dimension.) 
```python
newarr = arr.reshape(2, 2, -1)
```
✔️Flattening array means converting a multidimensional array into a 1D array.
We can use `reshape(-1)` to do this.
```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
newarr = arr.reshape(-1)   #[1 2 3 4 5 6]
```
