# 1295. Find Numbers with Even Number of Digits
Easy

165

26

Add to List

Share
Given an array nums of integers, return how many of them contain an even number of digits.
 

Example 1:

Input: nums = [12,345,2,6,7896]
Output: 2
Explanation: 
12 contains 2 digits (even number of digits). 
345 contains 3 digits (odd number of digits). 
2 contains 1 digit (odd number of digits). 
6 contains 1 digit (odd number of digits). 
7896 contains 4 digits (even number of digits). 
Therefore only 12 and 7896 contain an even number of digits.
Example 2:

Input: nums = [555,901,482,1771]
Output: 1 
Explanation: 
Only 1771 contains an even number of digits.


#### Runtime: 56 ms, faster than 81.72% of JavaScript online submissions for Find Numbers with Even Number of Digits.
#### Memory Usage: 35.5 MB, less than 100.00% of JavaScript online submissions for Find Numbers with Even Number of Digits.
```
var findNumbers = function(nums) {
    return nums.reduce((n, val) => { 
        return n + +(val.toString().length%2 === 0)
    }, 0)
};
```

---
#### Found the function to count length on the internet - suposedly fastest way buy haven't seen the difference
#### Runtime: 56 ms, faster than 81.54% of JavaScript online submissions for Find Numbers with Even Number of Digits.
#### Memory Usage: 34.5 MB, less than 100.00% of JavaScript online submissions for Find Numbers with Even Number of Digits.
```
var findNumbers = function(nums) {
    return nums.reduce((data, item) => { 
        return data + +(((Math.log(Math.abs(item)+1) * 0.43429448190325176 | 0) + 1)%2 === 0)
    }, 0)
};
```
