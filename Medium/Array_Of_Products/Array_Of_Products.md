# Array Of Products

Write a function that takes in a non-empty array of integers and returns an array of the same length,
where each element in the output array is equal to the product of every other number in the input array.
In other words, the value at output[i] is equal to the product of every number in the input array other
than input[i] .
Note that you're expected to solve this problem without using division.

```
Sample Input
array = [5, 1, 4, 2]

Sample Output
[8, 40, 10, 20]
// 8 is equal to 1 x 4 x 2
// 40 is equal to 5 x 4 x 2
// 10 is equal to 5 x 1 x 2
// 20 is equal to 5 x 1 x 4
```

![](/Medium/Array_Of_Products/IMG_0395.png)

Code:

```
function arrayOfProducts(array) {
  const l = array.length;
  let leftArr = new Array(l);
  let rightArr = new Array(l);
  leftArr[0] = 1;
  rightArr[l-1] = 1;

  for (let i = 1; i < array.length; i++) {
    leftArr[i] = leftArr[i-1] * array[i-1];
  }

  for (let i = l-2; i >= 0; i--) {
    rightArr[i] = rightArr[i+1] * array[i+1];
  }

  for (let i = 0; i < l; i++) {
    array[i] = leftArr[i] * rightArr[i];
  }

  return array;
}
```
