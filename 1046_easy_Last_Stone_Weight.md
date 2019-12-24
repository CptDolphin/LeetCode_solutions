We have a collection of rocks, each rock has a positive integer weight.

Each turn, we choose the two heaviest rocks and smash them together.  Suppose the stones have weights x and y with x <= y.  The result of this smash is:

If x == y, both stones are totally destroyed;
If x != y, the stone of weight x is totally destroyed, and the stone of weight y has new weight y-x.
At the end, there is at most 1 stone left.  Return the weight of this stone (or 0 if there are no stones left.)

 

Example 1:

Input: [2,7,4,1,8,1]
Output: 1
Explanation: 
We combine 7 and 8 to get 1 so the array converts to [2,4,1,1,1] then,
we combine 2 and 4 to get 2 so the array converts to [2,1,1,1] then,
we combine 2 and 1 to get 1 so the array converts to [1,1,1] then,
we combine 1 and 1 to get 0 so the array converts to [1] then that's the value of last stone.
 

Note:

1 <= stones.length <= 30
1 <= stones[i] <= 1000



---
#### Runtime: 100 ms, faster than 6.08% of JavaScript online submissions for Last Stone Weight.
#### Memory Usage: 38.3 MB, less than 100.00% of JavaScript online submissions for Last Stone Weight.
```javascript
var lastStoneWeight = function(stones) {
    while(stones.length >= 2){
        stones.sort((a, b) => a - b).reverse();
        console.log(stones);
        if(stones[0] === stones[1]){
            stones.splice(0,2);
        } else if(stones[0] > stones[1]){
            stones[0]-=stones[1];
            stones.splice(1,1);
        }
    }
    return stones;
};
```

---
#### Runtime: 60 ms, faster than 64.69% of JavaScript online submissions for Last Stone Weight.
#### Memory Usage: 34.8 MB, less than 100.00% of JavaScript online submissions for Last Stone Weight.
```javascript
var lastStoneWeight = function(stones) {
    stones.sort((a, b) => a - b);
    let h = -1;
    let s = -1;
    while(stones.length > 1){
        h = stones.pop();
        s = stones.pop();
        stones.push(Math.abs(h - s));
        stones.sort((a, b) => a - b);
<<<<<<< HEAD:1046_easy_Last_Stone_Weight.md
```
---
```javascript
var lastStoneWeight = function(stones) {
    stones.sort((a, b) => a > b ? -1 : 1);
    let h = -1;
    let s = -1;
    while(stones.length > 1){
        h = stones.shift();
        s = stones.shift();
        stones.push(Math.abs(h - s));
        stones.sort((a, b) => a > b ? -1 : 1);
    }
    return stones[0];
}
```
