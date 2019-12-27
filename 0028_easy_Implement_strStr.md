# 28. Implement strStr()
Easy

1177

1601

Add to List

Share
Implement strStr().

Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

Example 1:

Input: haystack = "hello", needle = "ll"
Output: 2
Example 2:

Input: haystack = "aaaaa", needle = "bba"
Output: -1
Clarification:

What should we return when needle is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().

---
#### Runtime: 52 ms, faster than 88.14% of JavaScript online submissions for Implement strStr().
#### Memory Usage: 33.8 MB, less than 89.29% of JavaScript online submissions for Implement strStr().
```javascript
var strStr = function(haystack, needle) {
    return haystack.indexOf(needle);
};
```
