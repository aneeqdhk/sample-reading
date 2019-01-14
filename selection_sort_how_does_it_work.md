# Selection Sort

The way selection sort works is that it divides the array into 2 parts: a sorted array and an unsorted array.

We repeatedly _select_ the **minimum element** from the unsorted array and place it in the sorted part, until our unsorted array is finished and all we are left with is the sorted array.

![Selection Sort](https://storage.googleapis.com/edyst-assets/static/selectionSort.gif)

Let's look at an example:

5, 2, 7, 3, 4, 8, 1, 6

We begin by holding the first element, and select the minimum from the remaining part of the array. If the minimum is lesser than the first element, we swap.

In this case, first element = 5, minimum element in rest of array is 1. Since 1 < 5, we swap.

Now the array is:

1, 2, 7, 3, 4, 8, 5, 6

Now, the minimum element is at the start of the array and thus it is in it's correct position. The array A[0] is sorted and we need to shift our attention to A[1] to A[7].

We will now hold A[1] and compare it with the minimum from A[2] to A[7]. A[1] = 2 and the minimum from the rest of the array is 3. Since 2 < 3, we don't swap.

The array remains:

1, 2, 7, 3, 4, 8, 5, 6

Now the array from A[0] to A[1] is sorted and we shift our focus to A[2] to A[7].

We will now hold A[2] and compare it with the minimum from A[3] to A[7]. A[2] = 7 and the minimum from the rest of the array is 3. Since 7 > 3, we will swap.

The array now becomes:

1, 2, 3, 7, 4, 8, 5, 6

Continuing on this trend, we get:

1, 2, 3, 4, 7, 8, 5, 6
1, 2, 3, 4, 5, 8, 7, 6
1, 2, 3, 4, 5, 6, 7, 8
1, 2, 3, 4, 5, 6, 7, 8
1, 2, 3, 4, 5, 6, 7, 8

**Steps for Selection Sort**

```
for i = 0 to n-1
    min = A[i], min_index = i
        for j = i+1 to n-1
            if (A[j] < min)
               {
                    min_index = j
                    min = A[j]
                }
        increment j
    swap(A[i], A[min_index])    
increment i
```

Have a look at [this visualization](https://visualgo.net/en/sorting)  and select selection sort, for more clarification.