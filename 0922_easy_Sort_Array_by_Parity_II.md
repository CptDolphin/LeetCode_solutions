922. Sort Array By Parity II
Easy

Given an array A of non-negative integers, half of the integers in A are odd, and half of the integers are even.

Sort the array so that whenever A[i] is odd, i is odd; and whenever A[i] is even, i is even.

You may return any answer array that satisfies this condition.

 

Example 1:

Input: [4,2,5,7]
Output: [4,5,2,7]
Explanation: [4,7,2,5], [2,5,4,7], [2,7,4,5] would also have been accepted.

 

Note:

    2 <= A.length <= 20000
    A.length % 2 == 0
    0 <= A[i] <= 1000

---
#### Runtime: 96 ms, faster than 71.55% of JavaScript online submissions for Sort Array By Parity II.
#### Memory Usage: 41.5 MB, less than 27.27% of JavaScript online submissions for Sort Array By Parity II.
```javascript
var sortArrayByParityII = function(A) {
    const odd = [];
    const even = [];
    const result = [];

    A.forEach(v => v%2 === 0 ? odd.push(v) : even.push(v));
    
    for(let i=0; i<Math.min(odd.length, even.length); i++){
        result.push(odd[i], even[i]);
    }
    
    return result;
};
```
