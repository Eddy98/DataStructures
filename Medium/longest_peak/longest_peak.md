# Longest Peak

Write a function that takes in an array of integers and returns the length of the longest peak in the array.
A peak is defined as adjacent integers in the array that are strictly increasing until they reach a tip (the
highest value in the peak), at which point they become strictly decreasing. At least three integers are
required to form a peak.
For example, the integers 1, 4, 10, 2 form a peak, but the integers 4, 0, 10 don't and neither do
the integers 1, 2, 2, 0 . Similarly, the integers 1, 2, 3 don't form a peak because there aren't any
strictly decreasing integers after the 3 .

```
Sample Input
array = [1, 2, 3, 3, 4, 0, 10, 6, 5, -1, -3, 2, 3]

Sample Output
6 // 0, 10, 6, 5, -1, -3
```

Idea: First attempt to find peaks. Then move left and right to see how long the peak is valid for. Keep track of the biggest peak.

Code:

```
function longestPeak(array) {
 // Write your code here.
 let currPeak = 0;
 let maxPeak = 0;
 for (let i = 0; i < array.length; i++) {
   if (isPeak(i, array)) {
     const left = checkLeft(i, array);
     const right = checkRight(i, array);
     currPeak = left + right + 1;
     maxPeak = Math.max(currPeak, maxPeak)
   }
 }
 return maxPeak;
}

function isPeak(index, array) {
 if (index === 0) return false;

 if (index === array.length-1) return false;

 if (array[index-1] < array[index] && array[index+1] < array[index])
   return true

 return false;
}

function checkLeft(index, array) {
 let count = 0;
 let prev = array[index];
 for (let i = index-1; i >= 0; i--) {
   if (prev <= array[i]) {
     return count;
   }
   count++;
   prev = array[i];
 }
 return count;
}

function checkRight(index, array) {
 let count = 0;
 let prev = array[index];
 for (let i = index+1; i < array.length; i++) {
   if (prev <= array[i]) {
     return count;
   }
   count++;
   prev = array[i];
 }
 return count;
}

```
