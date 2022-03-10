**Problem Statement**
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

 
**Examples**
Example 1:
```js
Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
```

Example 2:
```js
Input: nums = [0]
Output: [0]
```
 

Constraints:
```js
1 <= nums.length <= 104
-231 <= nums[i] <= 231 - 1
```

**Solution**
```js
const moveZeroes = (nums) => {
    let i = 0;
    let length = nums.length;
    while (i < length) {
      let curr = nums[i];
      if (curr === 0) {
        nums.splice(i, 1);
        nums.push(0);
        length--;
      } else {
        i++;
      }
    }
};
```

**Reference:**
https://leetcode.com/problems/move-zeroes/
