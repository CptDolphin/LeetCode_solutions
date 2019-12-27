# 804. Unique Morse Code Words

International Morse Code defines a standard encoding where each letter is mapped to a series of dots and dashes, as follows: "a" maps to ".-", "b" maps to "-...", "c" maps to "-.-.", and so on.

For convenience, the full table for the 26 letters of the English alphabet is given below:

[".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]
Now, given a list of words, each word can be written as a concatenation of the Morse code of each letter. For example, "cba" can be written as "-.-..--...", (which is the concatenation "-.-." + "-..." + ".-"). We'll call such a concatenation, the transformation of a word.

Return the number of different transformations among all words we have.

Example:
Input: words = ["gin", "zen", "gig", "msg"]
Output: 2
Explanation: 
The transformation of each word is:
"gin" -> "--...-."
"zen" -> "--...-."
"gig" -> "--...--."
"msg" -> "--...--."

There are 2 different transformations, "--...-." and "--...--.".
Note:

The length of words will be at most 100.
Each words[i] will have length in range [1, 12].
words[i] will only consist of lowercase letters.

---
```javascript
var uniqueMorseRepresentations = function(words) {
    return (new Set(words.map(word => word.split('').map(item => morse[item]).join('')))).size
};
```

---
#### Runtime: 60 ms, faster than 73.40% of JavaScript online submissions for Unique Morse Code Words.
#### Memory Usage: 36.4 MB, less than 27.78% of JavaScript online submissions for Unique Morse Code Words.
```javascript
var uniqueMorseRepresentations = function(words) {
    const alpha = {a: ".-",b: "-...",c: "-.-.",d: "-..",e: ".",f: "..-.",g: "--.",h: "....",i: "..",j: ".---",k: "-.-",l: ".-..",m: "--",n: "-.",o: "---",p: ".--.",q: "--.-",r: ".-.",s: "...",t: "-",u: "..-",v: "...-",w: ".--",x: "-..-",y: "-.--",z: "--.."};
    const result = new Set();
    const temp = [];
    for(let word of words){
            for(let letter of word){
                temp.push(alpha[letter]);
            }
        result.add(temp.join(''));
        temp.splice(0);
    }
    
    return result.size;
};
```

---
#### Runtime: 56 ms, faster than 89.44% of JavaScript online submissions for Unique Morse Code Words.
#### Memory Usage: 35.6 MB, less than 50.00% of JavaScript online submissions for Unique Morse Code Words.
```javascript
var uniqueMorseRepresentations = function(words) {
    const alpha = {a: ".-",b: "-...",c: "-.-.",d: "-..",e: ".",f: "..-.",g: "--.",h: "....",i: "..",j: ".---",k: "-.-",l: ".-..",m: "--",n: "-.",o: "---",p: ".--.",q: "--.-",r: ".-.",s: "...",t: "-",u: "..-",v: "...-",w: ".--",x: "-..-",y: "-.--",z: "--.."};
    return (new Set(words.map(word => word.split('').map(char => alpha[char]).join('')))).size
};
```
