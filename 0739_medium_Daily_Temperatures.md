# 739. Daily Temperatures
Medium

1882

58

Add to List

Share
Given a list of daily temperatures T, return a list such that, for each day in the input, tells you how many days you would have to wait until a warmer temperature. If there is no future day for which this is possible, put 0 instead.

For example, given the list of temperatures T = [73, 74, 75, 71, 69, 72, 76, 73], your output should be [1, 1, 4, 2, 1, 1, 0, 0].

Note: The length of temperatures will be in the range [1, 30000]. Each temperature will be an integer in the range [30, 100].

---

#### Runtime: 732 ms, faster than 37.51% of JavaScript online submissions for Daily Temperatures.
#### Memory Usage: 42.6 MB, less than 66.67% of JavaScript online submissions for Daily Temperatures.
#### Terribly brute force approach
```javascript
var dailyTemperatures = function(T) {
    const result = [];
    let length = 0;
    for(let i=0; i<T.length; i++){
        length = result.length;
        for(let j=i+1; j<T.length; j++){
            if(T[j] > T[i]){
                result.push(j-i);
                break;
            }
        }
        if(result.length === length){
            result.push(0);
        }
    }
    return result;
};
```

---
#### 

```javascript

```
