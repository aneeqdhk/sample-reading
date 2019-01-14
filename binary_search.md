# Binary Search

Binary search is a way of finding an element in a ***sorted array***. 

Binary search uses the property of a sorted array that the elements are arranged in a certain order.

Let's go through an example to understand Binary Search. 

Let's say my friend, Jyoti, wants me to give her pet dog a bath. 

However, Jyoti will not tell me the temperature of the water for the bath - I have to guess it. 

She will give me some hints though - whenever I guess, she will tell me if the number I guessed is higher than or lesser than the actual number. 

She also says that the temperature s between `0` and `100`

How would we go about guessing the temperature? The correct temperature was `29`. Here is how I found it:

> Me: Is the temperature 50?
> Jyoti: No! That's too high

Aha! So now we know that `50` **and every number greater than 50 is wrong!** So now we will guess only between `0` and `50`

> Me: Is the temperature 25?
> Jyoti: No! That's too low

We have got another hint! This means that the number is between `25` and `50`

> Me: Is the temperature 37? (mid-point of 25 & 50)
> Jyoti: Yes!

![binary_seach_comic](https://storage.googleapis.com/edyst-assets/static/Binary_search_comic.png)

Firstly, notice that we did _only_ 3 checks. Compare this with linear search - we would have had to do 37 checks!

So how did I guess the temperature? At every point, the hint that Jyoti gave me told me which values I could _ignore_. At every point I could cut down the possible values in half because of these hints.

In a similar way, sorted arrays also give us this hint. Since the array is sorted, let's say in ascending order, we know that the numbers at the start are less then or equal to the numbers after it.

Watch this video to understand Binary Search better: [Binary Search by Codearchery](https://www.youtube.com/watch?v=NfUTAymEfvQ)

**This is how binary search works:**

Given an Array, `A[]`, we want to find an element called `key` .

At first, we check the mid-point of the entire array. Here, we are considering the entire array: from index `0` to index `n-1`. And we check the mid-point of the array: `A[mid]`

![binary_seach_eg](https://storage.googleapis.com/edyst-assets/static/binary_search_eg_1.png)

We have three scenarios:
- `key` is at `A[mid]`: Great! We found the key!
- `key` is less than `A[mid]`: We need to consider the left side of the array
- `key` is greater than `A[mid]`: We need to consider the right side of the array

As you can see, we are always changing the size of the array in consideration. How do we keep a track of this?

We use 2 variables: `low` and `high`. `low` tells us the lowest index of the array in consideration. `high` tells us the highest index of the array in consideration.

- `mid` = `(high + low)/2`
- if `A[mid] == key`, return `mid` and break from the loop

The above steps are for calculating the mid-point and checking if our `key` value is equal to it

- if `A[mid] > key`, `high = mid - 1`
- If `A[mid] < key`, `low = mid + 1`

These 2 steps help us eliminate or ignore those parts of the array which we know don't contain our `key` value. 

If `A[mid] > key`, this means that our key value is less than the mid point and we have to check in the left side of the mid point. So, the `high` value has to become 1 less than the mid value.

If `A[mid] < key`, this means that our key value is greater than the mid point and we have to check in the right side of the mid point. So, the `low` value has to become 1 more than the mid value.

Till when do we continue doing this? We continue this until:
- The `key` value is found
- The entire array is searched and we have still not found our `key` value

Thus, our logic for this code looks like this:

1. `mid` = `(high + low)/2`
2. if `high < low`, break from loop and return `Not Found`
3. if `A[mid] == key`, return `mid` and break from the loop
4. if `A[mid] > key`, `high = mid - 1`
5. If `A[mid] < key`, `low = mid + 1`

***Line #2 deals with the condition of `Not Found`. ***

If the `key` is not present in our array, a time will come when the high value becomes lesser than the low value. When this condition is true then we know that the `key` value is not there and thus we should break from the loop.

### Program for Binary Search

```Java
    while(a[mid]!=key && high >= low) {
        mid = (high+low)/2;
        if(a[mid] == key)
            {
            	System.out.println("Found at " + mid);
            	break;
            } 
        else if(key > a[mid])
            {
            	low = mid + 1;
            }
        else if(key < a[mid])
            {
            	high = mid - 1;
            }
    }
```
