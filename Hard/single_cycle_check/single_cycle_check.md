# Single Cycle Check

You're given an array of integers where each integer represents a jump of its value in the array. For
instance, the integer 2 represents a jump of two indices forward in the array; the integer -3 represents
a jump of three indices backward in the array.
If a jump spills past the array's bounds, it wraps over to the other side. For instance, a jump of -1 at
index 0 brings us to the last index in the array. Similarly, a jump of 1 at the last index in the array
brings us to index 0 .
Write a function that returns a boolean representing whether the jumps in the array form a single cycle. A
single cycle occurs if, starting at any index in the array and following the jumps, every element in the array
is visited exactly once before landing back on the starting index.

```
Sample Input
array = [2, 3, 1, -4, -4, 2]

Sample Output
true
```

Idea: Move through array with a limited number of jumps. If after all jumps you are at the same index, then return true

![](/Hard/single_cycle_check/sincle_cycle.png)

Code: 

```
function hasSingleCycle(arr) {
  
  const startIndex = 0;
  let jumpCount = arr.length;
  const L = arr.length;
  let i = startIndex;

  while (jumpCount > 0) {
    let currVal = arr[i] % L; // EDGE CASE: If value is bigger than array size 
    if (currVal > 0) {
      if ((i+currVal) >= L) { // move back
        i -= (L-currVal);
      } else { //move forward
        i += currVal;
      }
    } else if (currVal < 0) {
      if (Math.abs(currVal) > i) { // move move forward
        i += (L-Math.abs(currVal));
      } else { // move back
        i -= Math.abs(currVal);
      }
    } else return false;
    if (arr[i] < 0 && Math.abs(arr[i]) === currVal) return false; // EDGE CASE - check for inner loops that make it not visit other places
    jumpCount--;
  }
  if (i === startIndex) return true;
  else return false;
}

// Do not edit the line below.
exports.hasSingleCycle = hasSingleCycle;

```
