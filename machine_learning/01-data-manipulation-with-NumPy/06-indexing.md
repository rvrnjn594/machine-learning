# Indexing

Index into NumPy arrays to extract data and array slices.

> We'll cover the following:
>
> - Chapter Goal:
>   A. Array accessing
>   B. Slicing
>   C. Argmin and argmax

## Chapter Goals:

- Learn about indexing arrays in NumPy
- Write code for indexing and slicing arrays

## A. Array accessing

Accessing NumPy arrays is identical to accessing Python lists.  
 For multi-dimensional arrays, it is equivalent to accessing Python lists of lists.

The code below shows example accesses of NumPy arrays.

    arr = np.array([1, 2, 3, 4, 5])
    print(arr[0])
    print(arr[4])

    arr = np.array([[6, 3], [0, 2]])
    # Subarray
    print(repr(arr[0]))

## B. Slicing

NumPy arrays also support slicing. Similar to Python, we use the colon operator (i.e. arr[:]) for slicing.  
 We can also use negative indexing to slice in the backwards direction.

The code below shows example slices of a 1-D NumPy array.

    arr = np.array([1, 2, 3, 4, 5])
    print(repr(arr[:]))
    print(repr(arr[1:]))
    print(repr(arr[2:4]))
    print(repr(arr[:-1]))
    print(repr(arr[-2:]))

For multi-dimensional arrays, we can use a comma to separate slices across each dimension.

The code below shows example slices of a 2-D NumPy array.

    arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
    print(repr(arr[:]))
    print(repr(arr[1:]))
    print(repr(arr[:, -1]))
    print(repr(arr[:, 1:]))
    print(repr(arr[0:1, 1:]))
    print(repr(arr[0, 1:]))

## C. Argmin and argmax

In addition to accessing and slicing arrays, it is useful **to figure out the actual indexes of the minimum and maximum elements.**  
 To do this, we **use the np.argmin and np.argmax functions.**

The code below shows example usages of np.argmin and np.argmax.  
Note that the index of element -6 is index 5 in the flattened version of arr.

    arr = np.array([[-2, -1, -3], [4, 5, -6], [-3, 9, 1]])
    print(np.argmin(arr[0])) # 2
    print(np.argmax(arr[2])) # 1
    print(np.argmin(arr)) # 5

The **np.argmin and np.argmax** functions take the same arguments.  
 The required argument is the input array and the axis keyword argument specifies which dimension to apply the operation on.

The code below shows how the axis keyword argument is used for these functions.

    arr = np.array([[-2, -1, -3],
                    [4, 5, -6],
                    [-3, 9, 1]])
    print(repr(np.argmin(arr, axis = 0))) # array([2, 0, 1])
    print(repr(np.argmin(arr, axis = 1))) # array([2, 2, 0])
    print(repr(np.argmax(arr, axis = -1))) # array([1, 1, 1])

- In our example, **using axis=0 meant the function found the index of the minimum row element for each column.**
- **When we used axis=1, the function found the index of the minimum column element for each row.**

Setting **axis to -1 just means we apply the function across the last dimension.**  
 In this case, axis=-1 is equivalent to axis=1.
