# Smallest Difference

Write a function that takes in two non-empty arrays of integers, finds the pair of numbers (one from each
array) whose absolute difference is closest to zero, and returns an array containing these two numbers,
with the number from the first array in the first position.
Note that the absolute difference of two integers is the distance between them on the real number line.
For example, the absolute difference of -5 and 5 is 10, and the absolute difference of -5 and -4 is 1.
You can assume that there will only be one pair of numbers with the smallest difference

Input

```
arrayOne = [-1, 5, 10, 20, 28, 3]
arrayTwo = [26, 134, 135, 15, 17]
```

Output

```
[28, 26]
```

![](/Medium/smallest_difference/IMG_0392.png)

Code:

```
function smallestDifference(arrayOne, arrayTwo) {
  arrayOne.sort((a,b) => a-b);
  arrayTwo.sort((a,b) => a-b);
  let min = Math.abs(arrayOne[0] - arrayTwo[0]);
  let i = 0; j = 0;
  let ans = [0, 0];

  while (i < arrayOne.length && j < arrayTwo.length) {
    const curr1 = arrayOne[i];
    const curr2 = arrayTwo[j];

    if (Math.abs(curr1 - curr2) < min) {
      min = Math.abs(curr1 - curr2);
      ans = [arrayOne[i], arrayTwo[j]];
    }

    if (curr1 < curr2)
      i++;
    else
      j++;
  };

  return ans
}
```
