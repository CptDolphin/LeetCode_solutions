70. Climbing Stairs
Easy

You are climbing a stair case. It takes n steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

Note: Given n will be a positive integer.

Example 1:

Input: 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps

Example 2:

Input: 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step



---
#### Runtime: 44 ms, faster than 97.57% of JavaScript online submissions for Climbing Stairs.
#### Memory Usage: 33.9 MB, less than 48.00% of JavaScript online submissions for Climbing Stairs.

**The algorithm for this problem is just fibonacci**
```javascript
var climbStairs = function(n) {
    return fib(n + 1);
    
    function fib(n, prev = []){
        let result = 0;
        if(n === 0){
            return 0;
        }
        
        if(prev[n] != null){
            return prev[n];
        }
        
        if(n <= 2){
            result = 1;
        } else {
            result = fib(n - 1, prev) + fib(n - 2, prev);
        }
        
        prev[n] = result;
        return result;
    }
};
```
