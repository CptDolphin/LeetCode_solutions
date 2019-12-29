# 917. Reverse Only Letters

Given a string S, return the "reversed" string where all characters that are not a letter stay in the same place, and all letters reverse their positions.

 

Example 1:

Input: "ab-cd"
Output: "dc-ba"
Example 2:

Input: "a-bC-dEf-ghIj"
Output: "j-Ih-gfE-dCba"
Example 3:

Input: "Test1ng-Leet=code-Q!"
Output: "Qedo1ct-eeLg=ntse-T!"
 

Note:

S.length <= 100
33 <= S[i].ASCIIcode <= 122 
S doesn't contain \ or "



---
#### old way
```javascript
var reverseOnlyLetters = function(S) {
    let arr = S.split('');
    let i = 0;
    let j = arr.length-1;
    let temp = 0;
    let re = /[a-zA-Z]/i
    while(i < j){
        if(arr[i].match(re) && arr[j].match(re)){
            temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
            i++;
            j--;
        } else if(!arr[i].match(re) && !arr[j].match(re)){
            i++;
            j--;
        } else if (arr[j].match(re)){
            // if only j matches, increase i - as it's a special character atm.
            i++;
        } else if (arr[i].match(re)){
            //same as above
            j--;
        }
    }
    return arr.join('');
};
```
---
#### Runtime: 52 ms, faster than 86.10% of JavaScript online submissions for Reverse Only Letters.
####Memory Usage: 34 MB, less than 75.00% of JavaScript online submissions for Reverse Only Letters.
```javascript
var reverseOnlyLetters = function(S) {
    const arr = S.split('');
    let i = 0;
    let j = S.length - 1;
    let temp = '';
    for(i, j; i < j && j > i;){
        if(/[a-zA-Z]/g.test(arr[i]) && /[a-zA-Z]/g.test(arr[j])){
            temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
            i++;
            j--;
        }
        
        if(!/[a-zA-Z]/g.test(arr[i])){
            i++;
        }
        
        if(!/[a-zA-Z]/g.test(arr[j])){
            j--;
        }
    }
    return arr.join('');
};
```

---
#### Runtime: 48 ms, faster than 96.03% of JavaScript online submissions for Reverse Only Letters.
#### Memory Usage: 33.7 MB, less than 100.00% of JavaScript online submissions for Reverse Only Letters.

```javascript
var reverseOnlyLetters = function(S) {
    const re = /[a-zA-Z]/g;
    const temp = S.match(re);
    if(!temp){
        return S;
    }
    return S.replace(re, () => temp.pop());
};
```
