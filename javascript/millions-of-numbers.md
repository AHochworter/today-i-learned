Date : 2024-02-20
Tags : #javascript #code-challenge
Millions-of-Numbers
Flush out numbers that are present in each of three different arrays of numbers.
Given three different (same size) arrays of numbers, iterate over each and only return the numbers that are present in all three.

Adrian and I worked on this Turing Prompt Code Challenge together. We thought the easiest solution would be to use the .includes method in conjunction with an AND statement.

Example :

```js
nums1 = [1, 2, 4, 5, 8];
nums2 = [2, 3, 5, 7, 9];
nums3 = [1, 2, 5, 8, 9];

const findMatches = (nums1, nums2, nums3) => {
  const matchesArray = nums1.filter(num => {
    return nums2.includes(num) && nums3.includes(num);
  });
  return matchesArray;
};

console.log(findMatches(nums1, nums2, nums3));
```
