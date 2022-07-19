# spiral traverse

Write a function that takes in an n x m two-dimensional array (that can be square-shaped when n == m)
and returns a one-dimensional array of all the array's elements in spiral order.
Spiral order starts at the top left corner of the two-dimensional array, goes to the right, and proceeds in a
spiral pattern all the way until every element has been visited.

```
Sample Input

array = [
 [1, 2, 3, 4],
 [12, 13, 14, 5],
 [11, 16, 15, 6],
 [10, 9, 8, 7],
]

Sample Output

[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16]

```

Code

```
function spiralTraverse(array) {
  const ans = [];
  let startRow = 0, startCol = 0;
  let endRow = array.length-1, endCol = array[0].length-1;

  while (startRow <= endRow && startCol <= endCol) {
    //Right
    for (let i = startCol; i <= endCol; i++) {
      ans.push(array[startRow][i]);
    }

    // Down
    for (let i = startRow + 1; i <= endRow; i++) {
      ans.push(array[i][endCol]);
    }

    // Left
    for (let i = endCol - 1; i >= startCol; i--) {
      if (endRow > startRow)
        ans.push(array[endRow][i]);
    }

    // Up
    for (let i = endRow - 1; i > startRow; i--) {
      if (endCol > startCol)
      ans.push(array[i][startCol]);
    }

    startRow += 1;
    endRow -= 1;
    startCol += 1;
    endCol -= 1;
  }

  return ans;
}

// Do not edit the line below.
exports.spiralTraverse = spiralTraverse;
```
