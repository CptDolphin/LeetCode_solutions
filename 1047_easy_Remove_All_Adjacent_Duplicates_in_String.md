# 1047. Remove All Adjacent Duplicates In String

Given a string S of lowercase letters, a duplicate removal consists of choosing two adjacent and equal letters, and removing them.

We repeatedly make duplicate removals on S until we no longer can.

Return the final string after all such duplicate removals have been made.  It is guaranteed the answer is unique.

 

Example 1:

Input: "abbaca"
Output: "ca"
Explanation: 
For example, in "abbaca" we could remove "bb" since the letters are adjacent and equal, and this is the only possible move.  The result of this move is that the string is "aaca", of which only "aa" is possible, so the final string is "ca".
 

Note:

1 <= S.length <= 20000
S consists only of English lowercase letters.


---
```javascript
var removeDuplicates = function(S) {
    let arr = [];
    for(let i=0; i<S.length; i++){
        if(arr[arr.length-1] === S[i]){
            arr.pop();
        } else {
            arr.push(S[i]);
        }
    }
    return arr.join('');
};
```
---
#### Runtime: 252 ms, faster than 19.01% of JavaScript online submissions for Remove All Adjacent Duplicates In String.
#### Memory Usage: 39.5 MB, less than 100.00% of JavaScript online submissions for Remove All Adjacent Duplicates In String.
```javascript
var removeDuplicates = function(S) {
    S = S.split('');
    let temp = 0;
    let prev = false;
    let length = -1;
    while(length !== S.length){
        length = S.length;
        prev = false;
        for(let i=0; i<S.length-1; i++){
            if(S[i] === S[i+1]){
                temp = i;
                prev = true;
                break;
            }
        }
        
        if(prev){
            S.splice(temp, 2);  
        }
    }
    
    return S.join('');
};
```
---
#### Runtime: 64 ms, faster than 98.27% of JavaScript online submissions for Remove All Adjacent Duplicates In String.
#### Memory Usage: 36.5 MB, less than 100.00% of JavaScript online submissions for Remove All Adjacent Duplicates In String.
```javascript
var removeDuplicates = function(S) {
    const re = /(qq|ww|ee|rr|tt|yy|uu|ii|oo|pp|ll|kk|jj|hh|gg|ff|dd|ss|aa|mm|nn|bb|vv|cc|xx|zz)/g
    while(true){
        let x = S.replace(re, '');
        if(S === x){
            return S;
        }
        S = x;
    }
};
```
