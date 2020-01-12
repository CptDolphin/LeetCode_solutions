# 1309. Decrypt String from Alphabet to Integer Mapping
Easy

68

7

Add to List

Share
Given a string s formed by digits ('0' - '9') and '#' . We want to map s to English lowercase characters as follows:

Characters ('a' to 'i') are represented by ('1' to '9') respectively.
Characters ('j' to 'z') are represented by ('10#' to '26#') respectively. 
Return the string formed after mapping.

It's guaranteed that a unique mapping will always exist.

 

Example 1:

Input: s = "10#11#12"
Output: "jkab"
Explanation: "j" -> "10#" , "k" -> "11#" , "a" -> "1" , "b" -> "2".
Example 2:

Input: s = "1326#"
Output: "acz"
Example 3:

Input: s = "25#"
Output: "y"
Example 4:

Input: s = "12345678910#11#12#13#14#15#16#17#18#19#20#21#22#23#24#25#26#"
Output: "abcdefghijklmnopqrstuvwxyz"
 

Constraints:

1 <= s.length <= 1000
s[i] only contains digits letters ('0'-'9') and '#' letter.
s will be valid string such that mapping is always possible.

#### Runtime: 48 ms, faster than 93.33% of JavaScript online submissions for Decrypt String from Alphabet to Integer Mapping.
#### Memory Usage: 34.1 MB, less than 100.00% of JavaScript online submissions for Decrypt String from Alphabet to Integer Mapping.
```javascript
const re = [['j', '10#'], ['k', '11#'], ['l', '12#'], ['m', '13#'], ['n', '14#'], ['o', '15#'], ['p', '16#'], ['q', '17#'], ['r', '18#'], ['s', '19#'], ['t', '20#'], ['u', '21#'], ['v', '22#'], ['w', '23#'], ['x', '24#'], ['y', '25#'], ['z', '26#'], ['a', '1'], ['b', '2'], ['c', '3'], ['d', '4'], ['e', '5'], ['f', '6'], ['g', '7'], ['h', '8'], ['i', '9']];

var freqAlphabets = function(s) {
    while(!(/[a-z]+/g).test(s)){
        re.forEach(regex => s = s.replace(new RegExp(regex[1], 'g'), regex[0]));
    }
    
    return s;
};
```
