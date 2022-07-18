# Move Element To End

You're given an array of integers and an integer. Write a function that moves
all instances of that integer in the array to the end of the array and returns
the array.
The function should perform this in place (i.e., it should mutate the input
array) and doesn't need to maintain the order of the other integers.

```
Sample Input
array = [2, 1, 2, 2, 2, 3, 4, 2]
toMove = 2
Sample Output
[1, 3, 4, 2, 2, 2, 2, 2] // the numbers 1, 3, and 4 could be ordered differently
```

![](/Medium/move_element_to_end/IMG_0394.png)

Code

```
function moveElementToEnd(array, toMove) {

  let forward = 0;
  let behind = 0;
  let count = 0;
  while(forward < array.length || behind < array.length) {
    if (forward < array.length) {
      if (array[forward] == toMove) {
        count++;
        forward++;
      } else {
        array[behind] = array[forward];
        behind++;
        forward++;
      }
    } else {
      array[behind] = toMove;
      behind++;
    }
  }
  return array;
}
```
