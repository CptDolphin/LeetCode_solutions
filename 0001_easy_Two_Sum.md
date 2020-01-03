# 0001 Two-sum 

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

---
#### Runtime: 108 ms, faster than 42.68% of JavaScript online submissions for Two Sum.
#### Memory Usage: 35.1 MB, less than 24.38% of JavaScript online submissions for Two Sum.
#### Brute-force approach
```javascript
var twoSum = function(nums, target) {
    if(nums == null || nums.length === 0){
        return nums;
    }

    for (let i = 0; i < nums.length; i++){
        for (let j = i+1; j < nums.length; j++){
            if (nums[j] == (target - nums[i])){
                return [i, j];
            }
        }
    }
    
    return {};
};
```
---
#### Runtime: 64 ms, faster than 61.84% of JavaScript online submissions for Two Sum.
#### Memory Usage: 34.5 MB, less than 88.02% of JavaScript online submissions for Two Sum.
#### With objects and arrays
```javascript
var twoSum = function(nums, target) {
    if(nums == null || nums.length === 0){
        return nums;
    }
    
    const hash = {}
    const result = [];
    
    for(let i=0; i<nums.length; i++){
        if(hash.hasOwnProperty(target - nums[i])){
            result[0] = hash[target - nums[i]];
            result[1] = i;
            break;
        } else {
            hash[nums[i]] = i;
        }
    }
    
    return result;
};
```
---
#### Runtime: 56 ms, faster than 85.07% of JavaScript online submissions for Two Sum.
#### Memory Usage: 34.4 MB, less than 89.67% of JavaScript online submissions for Two Sum.
#### With two arrays
```javascript
var twoSum = function(nums, target) {
    if(nums == null || nums.length === 0){
        return nums;
    }
    
    const temp = [];
    const result = [];

    for(let i=0; i<nums.length; i++){
        if(temp[target - nums[i]] >= 0){
            result.push(temp[target - nums[i]], i);
            break;
        } else {
            temp[nums[i]] = i;
        }
    }
    
    return result;
};
```
---
#### Runtime: 60 ms, faster than 72.73% of JavaScript online submissions for Two Sum.
#### Memory Usage: 37.1 MB, less than 8.68% of JavaScript online submissions for Two Sum.
```javascript
var twoSum = function(nums, target) {
    if(nums == null || nums.length === 0){
        return nums;
    }
    
    const obj = {};
    
    for(let [i, v] of nums.entries()){
        if(obj.hasOwnProperty(v)){
            return [obj[v], i];
        } else {
            obj[target - v] = i;
        }
    }
    
    return [];
};
```
---
#### Failed attempt works only in some cases
```javascript
var twoSum = function(nums, target) {
    if(nums == null || nums.length === 0){
        return nums;
    }
    
    const temp = [];
    
    for(let i=0; i<nums.length; i++){
        temp.push({ [nums[i]]: i });
    }

    temp.sort((a, b) => a - b);
    
    console.log(temp);
    
    let i = 0;
    let j = nums.length - 1;
    
    while(i < j){
        let x = parseInt(Object.keys(temp[i]));
        let y = parseInt(Object.keys(temp[j]));
        if(x + y === target){
            return [Object.values(temp[i]), Object.values(temp[j])];
        } else if (x + y < target){
            i++;
        } else {
            j--;
        }
    }
    
    return [];
};
```
---
