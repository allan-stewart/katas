# Water Retention Kata

(Adapted from http://www.geeksforgeeks.org/trapping-rain-water/)

## Objective

Create a method which takes an array of integers (representing an elevation map) and return the amount of water which could be held.

Example: `int calculateWaterRetention(int[] elevations)`


## Problem Description

In this kata, an array (or list) of integers represent elevations for a structure which may be able to hold water.
For example, the array `[2, 0, 2]` could be represented as a bucket like this:

```
| |
| |
---
```

That bucket can hold 2 units of water, represented by the `X`s below:

```
|X|
|X|
---
```

A similar array, `[2, 0, 3]` can also only hold 2 units of water, because water will run off in the places marked `.`:

```
..|
|X|
|X|
---
```

The input `[3, 0, 1, 0, 4]` would yield a structure that could hold 8 units of water, like this:

```
    |
|XXX|
|XXX|
|X|X|
-----
```

Here is a more complicated example for the input `[0, 3, 0, 2, 4, 2, 5, 3, 1]` which can hold 6 units of water:

```
      |  
    |X|  
 |XX|X||
 |X||||| 
 |X||||||
---------
```

## Testing Considerations

After getting the basic algorithm working, try exploring boundary cases like:

* Empty array
* Negative numbers
* Arrays containing non-integers (in languages which can support that, such as JavaScript)
* Non-array input
