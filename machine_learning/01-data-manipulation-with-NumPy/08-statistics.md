# Statistics

Learn how to apply statistical metrics to NumPy data.

> We'll cover the following:
>
> - Chaper Goals:
>   A. Analysis
>   B. Statistical metrics

## Chapter Goals:

- Learn about basic statistical analysis in NumPy
- Write code to obtain statistics for NumPy arrays

## A. Analysis

It is often useful to analyze data for its main characteristics and interesting trends.  
 There are few techniques in NumPy that allow us to quickly inspect data arrays.

> For example, we can obtain minimum and maximum values of a NumPy array using its inherent min and max functions.  
>  The gives us an initial sense of the data's range, and can alert us to extreme outliers in the data.

The code below shows example usages of min and max functions.

    arr = np.array([[0, 72, 3], [1, 3, -60], [-3, -2, 4]])

    print(arr.min())
    print(arr.max())

    print(repr(arr.min(axis=0)))
    print(repr(arr.max(axis=-1)))

The axis keyword argument is identical to how it was used in **np.argmin and np.argmax** from the chapter on Indexing.  
 In our example, we use axis=0 to find an array of the minimum values in each column of arr and axis=1 to find an array of the maximum values in each row of arr.

## B. Statistical metrics

NumPy also provides basic statistical functions such as **np.mean, np.var, and np.median, to calculate the mean, variance, and median of the data, respectively.**

The code below shows how to obtain basic statistics with NumPy.  
 Note that np.median applied without axis takes the median of the flattened array.

    arr = np.array([[0, 72, 3], [1, 3, -60], [-3, -2, 4]])
    print(np.mean(arr))
    print(np.var(arr))
    print(np.median(arr))
    print(repr(np.median(arr, axis=-1)))

Each of these functions takes in the data array as a required argument and axis as a keyword argument.  
 For a more comprehensive list of statistical functions (e.g. calculating percentiles, creating histograms, etc), check out the NumPy [statistics page](https://numpy.org/doc/stable/reference/routines.statistics.html).
