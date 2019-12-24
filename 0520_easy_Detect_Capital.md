# 520. Detect Capital
Easy

364

229

Add to List

Share
Given a word, you need to judge whether the usage of capitals in it is right or not.

We define the usage of capitals in a word to be right when one of the following cases holds:

All letters in this word are capitals, like "USA".
All letters in this word are not capitals, like "leetcode".
Only the first letter in this word is capital, like "Google".
Otherwise, we define that this word doesn't use capitals in a right way.
 

Example 1:

Input: "USA"
Output: True
 

Example 2:

Input: "FlaG"
Output: False
 

Note: The input will be a non-empty word consisting of uppercase and lowercase latin letters.

#### Runtime: 68 ms, faster than 35.81% of JavaScript online submissions for Detect Capital.
#### Memory Usage: 34.6 MB, less than 75.00% of JavaScript online submissions for Detect Capital.

```javascript
#### Terrible code where i went too far into the rabbit hole but works
var detectCapitalUse = function(word) {
    return word.split('').every(char => (char.charCodeAt(0) >= 65 && char.charCodeAt(0) <= 90)) || 
           word.split('').every(char => (char.charCodeAt(0) >= 97 && char.charCodeAt(0) <= 122)) || 
          (word.charAt(0).charCodeAt(0) >= 65 && word.charAt(0).charCodeAt(0) <= 90 && 
           word.split('').splice(1).every(char => (char.charCodeAt(0) >= 97 && char.charCodeAt(0) <= 122)));
};
```
---

#### Runtime: 64 ms, faster than 60.38% of JavaScript online submissions for Detect Capital.
#### Memory Usage: 34.1 MB, less than 100.00% of JavaScript online submissions for Detect Capital.
```javascript
var detectCapitalUse = function(word) {
    if(/^([A-Z]?)[a-z]+$/g.test(word)){
        return true;
    } else if (/^[A-Z]+$/g.test(word)){
        return true;
    } else {
        return false;
    }
};
```
---

#### Runtime: 52 ms, faster than 96.40% of JavaScript online submissions for Detect Capital.
#### Memory Usage: 34.2 MB, less than 100.00% of JavaScript online submissions for Detect Capital.
```javascript
var detectCapitalUse = function(word) {
    const regexes = [/^([A-Z]?)[a-z]+$/g, /^[A-Z]+$/g];
    return regexes.filter(regex => regex.test(word)).length > 0;
};
```
---


