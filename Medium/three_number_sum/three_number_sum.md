# Three Number Sum

Write a function that takes in a non-empty array of distinct integers and an
integer representing a target sum. The function should find all triplets in
the array that sum up to the target sum and return a two-dimensional array of
all these triplets. The numbers in each triplet should be ordered in ascending
order, and the triplets themselves should be ordered in ascending order with
respect to the numbers they hold.

![](/Medium/three_number_sum//3sum.jpg)

```
function threeNumberSum(array, targetSum) {
let ans = [];
const sorted = array.sort((a,b) => a-b)
sorted.forEach((curr, index) => {
  const tempTaget = targetSum - curr
  twoSum(sorted, tempTaget, ans, index + 1)
})
return ans
}

const twoSum = (arr, tempTarget, ans, start) => {
const set = new Set()

for (let i = start; i < arr.length; i++) {
  const check = tempTarget - arr[i]
  if (set.has(check)) {
    const arrToAdd = [arr[i], check, arr[start-1]]
    arrToAdd.sort()
    ans.push(arrToAdd)
  } else {
    set.add(arr[i])
  }
}
}
```
