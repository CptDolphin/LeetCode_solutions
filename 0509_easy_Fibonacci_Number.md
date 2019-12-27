# 509 Fibbonacci Numbers
The Fibonacci numbers, commonly denoted F(n) form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1. That is,

F(0) = 0,   F(1) = 1
F(N) = F(N - 1) + F(N - 2), for N > 1.
Given N, calculate F(N).

 

Example 1:

Input: 2
Output: 1
Explanation: F(2) = F(1) + F(0) = 1 + 0 = 1.
Example 2:

Input: 3
Output: 2
Explanation: F(3) = F(2) + F(1) = 1 + 1 = 2.
Example 3:

Input: 4
Output: 3
Explanation: F(4) = F(3) + F(2) = 2 + 1 = 3.
 

Note:

0 ≤ N ≤ 30.
---
#### easiest recursive
```javascript
function fib(n){
    if(n === 0) return 0;
    if(n <= 2) return 1;
    return fib(n-1) + fib(n-2);
}
```

#### iterative from 0 till we get to n
```javascript
function fib(n){
    let a = 1;
    let b = 0;
    let temp = 0;
    
    while(n > 0){
        temp = a;
        a += b;
        b = temp;
        n--;
    }
    return b
}
```

---
#### recursive 
```javascript
function fib(n){
    let result = 0;
    if(n === 0){
        return 0;
    }
    
    if(n <= 2){
        result = 1;
    } else {
        result = fib(n-1) + fib(n-2);
    }
    return result;
}
```
---
#### recursive with caching
```javascript
function fib(n, prev = []){
    let result = 0;
    if(n === 0){
        return 0;
    }
    
    if(prev[n] != null){
        return prev[n];
    }
    
    if(n <= 2) {
        result = 1;
    } else {
        result = fib(n-1, prev) + fib(n-2, prev);
    }
    
    prev[n] = result;
    return result;
}
```
