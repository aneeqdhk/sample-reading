# Sorting Algorithms

Sorting Algorithms are algorithms that put elements in an array in the correct order. 

We will see sorting algorithms that put the elements in ***ascending order***. 

You can easily modify those to make it in descending order too.

# Bubble Sort

Bubble sort is the simplest sorting algorithm. This also causes it to be quite slow (we'll see in later sections how to estimate the speed of an algorithm).

Bubble sort works by repeatedly swapping adjacent elements if they are in the wrong order.

### Logic for Bubble Sort

![binary_seach_eg](https://storage.googleapis.com/edyst-assets/static/Bubble-sort.gif)

Can you notice what is happening?

We go through the array, again and again. At each step we compare 2 adjacent elements. Are they in the correct order? If they are: we move on. If they are not: we swap them. Then, move to the next pair.

At the end of the first iteration, the maximum element of the array comes to the end. If the maximum element is at the end, then it is in it's correct place. This means we now have to sort the remaining part of the array. 

So, in the next iteration, we will only repeat till the second last index. Now the second highest element will be in the second last index. 

And thus, in every iteration we reduce the array we are sorting.

Let's take an example - we shall sort the array `5 1 4 2 8` using Bubble Sort.

**First Iteration**

( **5** **1** 4 2 8 ) ->  ( **1** **5** 4 2 8 ), Here, algorithm compares the first two elements, and swaps since 5 > 1

( 1 **5** **4** 2 8 ) ->  ( 1 **4** **5** 2 8 ), Swap since 5 > 4

( 1 4 **5** **2** 8 ) -> ( 1 4 **2** **5** 8 ), Swap since 5 > 2

( 1 4 2 **5** **8** ) ->  ( 1 4 2 **5** **8** ), Now, since these elements are already in order (8 > 5), algorithm does not swap them.

As we can see, the highest element, **8** has come to the end of the array. 

**Second Iteration**

We need to iterate only till n-2 index, which is A[3]

( **1** **4** 2 5 8 ) ->  ( **1** **4** 2 5 8 )

( 1 **4** **2** 5 8 ) ->  ( 1 **2** **4** 5 8 ), Swap since 4 > 2

( 1 2 **4** **5** 8 ) ->  ( 1 2 **4** **5** 8 )


**Third Iteration**

We need to iterate only till A[2]

( **1** **2** 4 5 8 ) ->  ( **1** **2** 4 5 8 )

( 1 **2** **4** 5 8 ) ->  ( 1 **2** **4** 5 8 )

**Fourth Iteration**

We need to iterate only till A[1]

( **1** **2** 4 5 8 ) ->  ( **1** **2** 4 5 8 )

Now the algorithm ends and our array is sorted!

Let's look at the steps of this Bubble Sort:

```
for i = 0 to n - 1
    for j = 0 to n - i
        if A[j] > A[j+1]
            {
                swap A[j] and A[j+1]
            }
        increment j
increment i
```

Have a look at [this visualization](https://visualgo.net/en/sorting)  and select bubble sort, for more clarification.

