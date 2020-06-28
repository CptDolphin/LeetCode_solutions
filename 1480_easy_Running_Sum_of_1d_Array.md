# 1480. Running Sum of 1d Array
Easy

168

29

Add to List

Share
Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).

Return the running sum of nums.

 

Example 1:

Input: nums = [1,2,3,4]
Output: [1,3,6,10]
Explanation: Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].
Example 2:

Input: nums = [1,1,1,1,1]
Output: [1,2,3,4,5]
Explanation: Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].
Example 3:

Input: nums = [3,1,2,10,1]
Output: [3,4,6,16,17]

---
#### Runtime: 76 ms, faster than 35.09% of JavaScript online submissions for Running Sum of 1d Array.
#### Memory Usage: 42 MB, less than 100.00% of JavaScript online submissions for Running Sum of 1d Array.
#### Bad attempt at writing it - haven't written code in months, getting back to it.

```javascript
var runningSum = function(nums) {
    const result = [];
    for(let i=0; i<nums.length; i++){
        result[i] = nums.slice(0, i+1).reduce((a, b) => a + b);
    }
    
    return result;
};
```

---
#### Runtime: 72 ms, faster than 63.37% of JavaScript online submissions for Running Sum of 1d Array.
#### Memory Usage: 35.9 MB, less than 100.00% of JavaScript online submissions for Running Sum of 1d Array.
#### kinda more obvious approach - searching for even faster log0 time complexity solution
```javascript
var runningSum = function(nums) {
    const result = [];
    let num = 0;
    
    for(let i=0; i<nums.length; i++){
        num += nums[i];
        result[i] = num;
    }
    
    return result;
};
```
---
#### Runtime: 8 ms, faster than 71.80% of C online submissions for Running Sum of 1d Array.
#### Memory Usage: 6.6 MB, less than 100.00% of C online submissions for Running Sum of 1d Array.
#### Not my solution, found it on the net but getting interested in C lang
```c
int* runningSum(int* nums, int numsSize, int* returnSize){
    for(*returnSize = numsSize; --numsSize && nums++; nums[0] += nums[-1]);
    return nums - *returnSize + 1;
}
```
