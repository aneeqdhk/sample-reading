# For Loop

In most programming languages, we get more than one way of writing loops. A very common loop is called the **for loop**.

### What is the for loop?

In the `while` loop, we were only checking a certain condition and executing the statements within it. The loop itself did not declare the variable. The `while` loop also did not give the initial value to the variable.

Example:
```Java
int num = 11; //Declaring the number is NOT part of the while loop
        while(num <= 20){ //ONLY the condition is part of the while loop
            System.out.println(num); // printing the numbers at every step
            num++; //incrementing the number is not part of while loop syntax. We are doing it separately 
        }
```

On the other hand, in the `for` loop we delcare and increment the counter variable in the loop itself.

Let's look at the syntax:

```Java
for(int i =1; i<=10; i++) // created i, and also incremented it as PART of the loop
    {
        System.out.println(i);
    }
```

Output:
```
1
2
3
4
5
6
7
8
9
10
```

What happened here?

1. Firstly, the variable `i` was declared and initialized to `1`
2. Secondly, the condition was tested: `i<=10` and this returned `true`. Since it is `true`, we enter into the body of the loop. If it is `false`, the loop is over
3. Third, the **statements** were executed: `System.out.println(i);`. Notice that the statement is using the value of `i`
4. After this, an increment is done `i++`
5. And then steps #2, #3 and #4 are repeated

Note: The initialization & declaration happens **only once**.

Also, the increment, happens only **after** the statements are executed.

We can summarize the suntax like this:

```
for (initialization; termination; increment) 
{
    statements
}
```

---

The flowchart of `for` loop:

![For Loop Flowchart](https://storage.googleapis.com/edyst-assets/static/for-loop.jpg)


### Examples

**Example #1**

Writing a `for` loop to print the numbers 10 to 1, in descending order.

```Java
for (int i = 10; i >= 1; i--)
    {
        System.out.println(i);
    }
```

**Example #2**

Writing a `for` loop to print 5 asterisks `*`

```Java
for (int i = 1; i <= 5; i++)
    {
        System.out.print("*");
    }
```
Output: (Note, we used `System.out.print` to print without going to a new line).
```
*****
```

**Example #3**

Writing a `for` loop to print 5 multiples of a number `num`

```Java
for (int i = 1; i <= 5; i++)
    {
        System.out.println(num*i);
    }
```
Output (with `num` = 3)
```
3
6
9
12
15
```

---

You can watch the following Videos to understand more about for loops:

[For Loop Tutorial #1](https://www.youtube.com/watch?v=cVGK_oO-n1A)

[For Loop Tutorial #2](https://www.youtube.com/watch?v=r2d95nDxfME)

Go ahead and try out some examples yourself!