# First Duplicate Value

Given an array of integers between 1 and n , inclusive, where n is the length of the array, write a
function that returns the first integer that appears more than once (when the array is read from left to
right).
In other words, out of all the integers that might occur more than once in the input array, your function
should return the one whose first duplicate value has the minimum index.
If no integer appears more than once, your function should return -1 .
Note that you're allowed to mutate the input array.

```
Sample Input #1
array = [2, 1, 5, 2, 3, 3, 4]
Sample Output #1
2 // 2 is the first integer that appears more than once.
// 3 also appears more than once, but the second 3 appears after the second 2.


Sample Input #2
array = [2, 1, 5, 3, 3, 2, 4]
Sample Output #2
3 // 3 is the first integer that appears more than once.
// 2 also appears more than once, but the second 2 appears after the second 3.
```

Best approach: O(1) space, O(n) time - use the same array to mark the values that you have seen. Since the values are constraint from 1 to N. You can mark a value as "seen" by marking the position arr[currValue-1] by making its value negative. if you run into a negative again, then its the first duplicate!!! Note: remember to check if the currValue has been change to negative before accessing the array! or you can just use the absolute value.

Code:

```
function firstDuplicateValue(array) {
  // Write your code here.
  let ans = -1;
  for(let i = 0; i < array.length; i++) {
    let currVal = array[i];
    if (currVal < 0) currVal *= -1; // if value has been changed to negative, change it back
    if (array[currVal-1] < 0 && ans === -1) {
      console.log('here')
      ans = currVal;
    }

    array[currVal-1] = array[currVal-1] * -1;
  }

  return ans;
}
```
