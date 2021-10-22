# Numpy Arrays

```python
> myarray.shape
(50, 5)   # for a 2D array / matrix with 50 rows and 5 columns

# just get row count .. use slice notation
> myarray.shape[0]
50

# just get cols count
> myarray.shape[1]
5
```

**Reshaping Arrays**

```
Reshape your data either using array.reshape(-1, 1) if your data has a single feature or array.reshape(1, -1) if it contains a single sample.
```
