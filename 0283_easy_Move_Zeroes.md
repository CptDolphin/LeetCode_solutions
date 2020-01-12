# 283. Move Zeroes
Easy

2772

98

Add to List

Share
Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Example:

Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
Note:

You must do this in-place without making a copy of the array.
Minimize the total number of operations.j

---

#### Runtime: 44 ms, faster than 100.00% of JavaScript online submissions for Move Zeroes.
#### Memory Usage: 36.2 MB, less than 17.02% of JavaScript online submissions for Move Zeroes.
```javascript
var moveZeroes = function(nums) {
    let pos = 0;
    nums.map(val => {
        if(val !== 0){
            nums[pos++] = val;
        }
    });
    
    return nums.map(val => {
        if(pos < nums.length) {
            nums[pos++] = 0;
        }
    });
};
```
---
```javascript
var moveZeroes = function(nums) {
    for(let i = nums.length - 1; i >= 0; i--) {
        if(nums[i] === 0) {
            nums.splice(i, 1);
            nums.push(0);
        }
    }
    
    return nums;
};
```
---
#### This one doesnt mutate passed array but creates a new one, so didn
t pass the test casess
```javascript
    return nums.reduceRight((data, item) => {
        if(item === 0){
            data.total.push(item);
        } else {
            data.total.unshift(item);
        }
        return data;
    },  {total: []});
```
