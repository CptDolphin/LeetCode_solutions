# 453. Minimum Moves to Equal Array Elements
Easy

448

669

Add to List

Share
Given a non-empty integer array of size n, find the minimum number of moves required to make all array elements equal, where a move is incrementing n - 1 elements by 1.

Example:

Input:
[1,2,3]

Output:
3

Explanation:
Only three moves are needed (remember each move increments two elements):

[1,2,3]  =>  [2,3,3]  =>  [3,4,3]  =>  [4,4,4]

---
#### Runtime: 68 ms, faster than 63.08% of JavaScript online submissions for Minimum Moves to Equal Array Elements.
#### Memory Usage: 37.7 MB, less than 100.00% of JavaScript online submissions for Minimum Moves to Equal Array Elements

```javascript
var minMoves = function(nums) {
    const min = Math.min(...nums);
    return nums.reduce((a, b) => a + b) - min * nums.length;
}
```
---
```javascript
var minMoves = function(nums) {
    const min = Math.min(...nums);
    return nums.map(num => num - min).reduce((a, b) => a + b);
};
```
---
```javascript
var minMoves = function(nums) {
    let sum = 0;
    let min = Number.MAX_SAFE_INTEGER;
    
    for(let num of nums){
        min = (num < min) ? num : min;
        sum += num;
    }
    
    return sum - min * nums.length;
    
};
```
