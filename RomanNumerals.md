# Roman Numerals Kata

## Objective

Convert integers into [Roman Numerals](http://en.wikipedia.org/wiki/Roman_numerals) and/or visa versa.

Example: `string toRoman(int input)` or `int fromRoman(string input)`

## Problem Description

The seven symbols used in Roman numerals are:

* `I` = 1
* `V` = 5
* `X` = 10
* `L` = 50
* `C` = 100
* `D` = 500
* `M` = 1000

Numeric values are created by combining symbols using the largest values possible
until you reach the desired value.
For example, `VII` equals 7 and `XXVI` equals 26.

However, there are a few specific cases where a subtractive notation is used:

* `IV` = 4
* `IX` = 9
* `XL` = 40
* `XC` = 90
* `CD` = 400
* `CM` = 900

So for example, `XCV` equals 95 and `MMXIV` equals 2014.

## Testing Considerations

After getting the basic algorithm working, try exploring boundary cases like:

* Zero (there is no roman numeral for 0)
* Negative numbers
* Invalid input

## Challenges

* Implement this kata using functional programming
* Use a reduce function instead of a loops
* Use recursion instead of loops
