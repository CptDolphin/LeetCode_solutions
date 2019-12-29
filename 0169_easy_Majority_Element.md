# 169. Majority Element
Easy

Given an array of size n, find the majority element. The majority element is the element that appears more than ⌊ n/2 ⌋ times.

You may assume that the array is non-empty and the majority element always exist in the array.

Example 1:

Input: [3,2,3]
Output: 3

Example 2:

Input: [2,2,1,1,1,2,2]
Output: 2




---
#### Runtime: 60 ms, faster than 84.95% of JavaScript online submissions for Majority Element.
#### Memory Usage: 37.1 MB, less than 85.71% of JavaScript online submissions for Majority Element.
```javascript
var majorityElement = function(nums) {
    const obj = {};
    nums.forEach(num => obj[num] = 1 + (obj[num] || 0));
    return Object.keys(obj).find(val => obj[val] === Math.max(...Object.values(obj)));
};
```

---
#### Runtime: 68 ms, faster than 50.81% of JavaScript online submissions for Majority Element.
#### Memory Usage: 37.6 MB, less than 57.14% of JavaScript online submissions for Majority Element.
```javascript
var majorityElement = function(nums) {
    const obj = {};
    const majority = nums.length/2;
    
    for(let i=0; i<nums.length; i++){
        obj[nums[i]] = 1 + (obj[nums[i]] || 0);
        if(obj[nums[i]] > majority){
            return nums[i];
        }
    }
};
```
