# 448. Find All Numbers Disappeared in an Array
Easy

Given an array of integers where 1 ≤ a[i] ≤ n (n = size of array), some elements appear twice and others appear once.

Find all the elements of [1, n] inclusive that do not appear in this array.

Could you do it without extra space and in O(n) runtime? You may assume the returned list does not count as extra space.

Example:

Input:
[4,3,2,7,8,2,3,1]

Output:
[5,6]

---
#### Not working yet the for loop almost worked but edge cases were missed - tbc.
```javascript
const result = [];
    const arr = [...new Set(nums.sort((a, b) => a - b))];
    
    if(arr.length === 1){
        if(arr[0] === 1){
        return [arr[0]+1];
        } else {
            return [arr[0]-1];
        }
    }

    for(let i=1; i<arr.length; i++){
        if(arr[i] - arr[i-1] !== 1){
            result.push(...[...new Array(arr[i] - arr[i-1] - 1).keys()].map(key => key + i + 1));
        }
    }
    return result;
```
---
#### Runtime: 4968 ms, faster than 22.40% of JavaScript online submissions for Find All Numbers Disappeared in an Array.
#### Memory Usage: 61.6 MB, less than 12.50% of JavaScript online submissions for Find All Numbers Disappeared in an Array.
#### Terribly slow with the indexOf 
```javascript
var findDisappearedNumbers = function(nums) {
    const arr = [...new Set(nums.sort((a, b) => a - b))];
    
    const temp = Array.from(new Array(nums.length), (v, i) => i + 1);
    const result = [];    
    
    for (let i = 0; i < temp.length; i++) {
        if(arr.indexOf(temp[i]) === -1){
            result.push(temp[i]);
        }
    }

    return result;
};
```
