# Aggregation

Use aggregation techniques to combine NumPy data and arrays.

> We'll cover the following:
>
> - Chapter Goals:
>   A. Summation
>   B. Concatenation

## Chapter Goals:

- Learn how to aggregate data in NumPy
- Write code to obtain sums and concatenations of NumPy arrays

## A. Summation

As we know how to calculate the sum of individual values between multiple arrays.  
 To sum the values within a single array, we use the np.sum function.

The function takes in a NumPy array as its required argument, and uses the axis keyword argument.  
 If the axis keyword argument is not specified, np.sum returns the overall sum of the array.

The code below shows how to use np.sum:

    arr = np.array([[0, 72, 3], [1, 3, -60], [-3, -2, 4]])

    print(np.sum(arr))
    print(repr(np.sum(arr, axis=0)))
    print(repr(np.sum(arr, axis=1)))

In addition to regular sums, NumPy can **perform cumulative sums using np.cumsum.**  
 Like np.sum, np.cumsum also takes in a NumPy array as a required argument and uses the axis argument.

If the **axis keyword argument is not specified, np.cumsum will return the cumulative sums for the flattened array**.

> The code below shows how to use np.cumsum.  
> For a 2-D NumPy array, setting axis=0 returns an array with cumulative sums across each column, while axis=1 returns the array with cumulative sums across each row.
>
> Not setting axis returns a cumulative sum across all teh values of the flattend array.

    arr = np.array([[0, 72, 3], [1, 3, -60], [-3, -2, 4]])
    print(repr(np.cumsum(arr)))
    print(repr(np.cumsum(arr, axis=0)))
    print(repr(np.cumsum(arr, axis=1)))

## B. Concatenation

An important part of aggregation is combining multiple datasets. In NumPy, this equates to combining multiple arrays into one.  
 The function we use to do this is **np.concatenate.**  
 Like the summation functions, np.concatenate uses the axis keyword argument.

However, the default value for axis is 0 (i.e. dimension 0).

Furthermore, the required argument for np.concatenate is a list of arrays, which the function combines into a single array.

The code below shows how to use np.concatenate, which aggregate arrays by joining them along a specific dimension.  
 For 2-D arrays, not setting the axis argument (defaults to axis=0) concatenate the arrays vertically.  
 When we set axis=1, the arrays are concatenated horizontally.

    arr1 = np.array([[0, 72, 3], [1, 3, -60], [-3, -2, 4]])
    arr2 = np.array([[-15, 6, 1], [8, 9, -4], [5, -21, 18]])

    print(repr(np.concatenate([arr1, arr2]))) # default axis is 0
    print(repr(np.concatenate([arr1, arr2], axis=1)))
    print(repr(np.concatenate([arr2, arr1], axis=1)))
