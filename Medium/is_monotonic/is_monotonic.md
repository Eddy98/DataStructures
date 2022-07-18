# Is Monotonic

Write a function that takes in an array of integers and returns a boolean representing whether the array is
monotonic.
An array is said to be monotonic if its elements, from left to right, are entirely non-increasing or entirely
non-decreasing.
Non-increasing elements aren't necessarily exclusively decreasing; they simply don't increase. Similarly,
non-decreasing elements aren't necessarily exclusively increasing; they simply don't decrease.
Note that empty arrays and arrays of one element are monotonic.

```
Sample Input
array = [-1, -5, -10, -1100, -1100, -1101, -1102, -9001]

Sample Output
true
```

Code

```
function isMonotonic(array) {
  // Write your code here.
  if (array.length === 0 || array.length === 1) return true;
  let isIncreasing;
  let isMono = true;

  let i = 0, j = 1;
  while (i < array.length && j < array.length) {
    if (isIncreasing === undefined) {
      if (array[i] < array[j]) {
        isIncreasing = true
      } else if (array[i] > array[j]) {
        isIncreasing = false;
      } else {
        i++;
        j++;
      }
    } else {
      if (isIncreasing) {
        if (array[i] > array[j]) return false;
      } else {
        if (array[i] < array[j]) return false;
      }
      i++;
      j++;
    }
  }

  return true;
}
```
