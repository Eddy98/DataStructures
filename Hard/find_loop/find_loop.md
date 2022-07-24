# Find Loop

Write a function that takes in the head of a Singly Linked List that contains a loop (in other words, the list's
tail node points to some node in the list instead of None / null ). The function should return the node
(the actual node--not just its value) from which the loop originates in constant space.
Each LinkedList node has an integer value as well as a next node pointing to the next node in the
list.

```
Sample Input
head = 0 -> 1 -> 2 -> 3 -> 4 -> 5 -> 6 // the head node with value 0
 ^ v
 9 <- 8 <- 7

Sample Output
4 -> 5 -> 6 // the node with value 4
^ v
9 <- 8 <- 7
```

IDEA:
Solution one is very straight forward, giving us a O(n) solution for time and space.

Solution two is more complicated. Using math we can proof that By having 2 pointers starting at index 0, and having them move forward. Pointer 1 moving one index at a time, and Pointer 2 moving two indexes at a time, once they meet, we know that their distance to the LOOP NODE is the same that the distance from the HEAD to the LOOP NODE. We move one to the head, and once they collide, we know that that is the LOOP NODE

Code:

```
// This is an input class. Do not edit.
class LinkedList {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

function findLoop(head) {
  const set = new Set();

  let curr = head;

  while(curr != null) {

    if (set.has(curr)) {
      break;
    }
    set.add(curr);
    curr = curr.next;

  }

  return curr;
}

// Solution 2

// This is an input class. Do not edit.
class LinkedList {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

function findLoop(head) {
  let i = head.next, j = head.next.next;

  while(true) {
    if (i === j) {
      i = head;
      while(true) {
        if (i === j) break;
        i = i.next;
        j = j.next;
      }
      break;
    }
    i = i.next;
    j = j.next.next;
  }
  return i;
}

// Do not edit the lines below.
exports.LinkedList = LinkedList;
exports.findLoop = findLoop;

```
