# Fibonacci Variations

## Objective

Create a method/function that returns the nth Fibonacci number in the sequence: 1, 1, 2, 3, 5, 8...

Example: `int Fibonacci(int input)`

Then once you have your first implementation working, try to create as many other variations as you can.

## Testing

Here are some basic test cases to get you started:

```
input  expected
-----  --------
0      0
1      1
2      1
3      2
4      3
5      5
6      8
7      13
8      21
9      34
10     55
```

Note that for this kata, we define the 0th Fibonacci number to be zero.

The return value for negative inputs or for large numbers (which may cause integer overflows) are not defined for this kata.

## Variations

The Fibonacci sequence is relatively simple to implement, which means that the meat of this kata lies in trying various ways to implement it.
Here are some ideas you might try:

* Use a `for` loop
* Use recursion
* Use a dictionary
* Use a list
* Use a hash or dictionary
* Use a stack
* An iterator or generator
    * (e.g. `yield return`)
* Cache intermediate results so they are only ever calculated once

You may also consider putting constraints on your implementation, such as:
* Don't allow `if` statements or ternaries
* Make your function operate in O(n) time or better
* No method may be more than 3 lines
