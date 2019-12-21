<<<<<<< HEAD
# 933. Number of Recent Calls
=======
933. Number of Recent Calls
>>>>>>> 4dfa857... rename test
Easy

Write a class RecentCounter to count recent requests.

It has only one method: ping(int t), where t represents some time in milliseconds.

Return the number of pings that have been made from 3000 milliseconds ago until now.

Any ping with time in [t - 3000, t] will count, including the current ping.

It is guaranteed that every call to ping uses a strictly larger value of t than before.

 

Example 1:

Input: inputs = ["RecentCounter","ping","ping","ping","ping"], inputs = [[],[1],[100],[3001],[3002]]
Output: [null,1,2,3,3]

 

Note:

    Each test case will have at most 10000 calls to ping.
    Each test case will call ping with strictly increasing values of t.
    Each call to ping will have 1 <= t <= 10^9.

<<<<<<< HEAD
---
#### Runtime: 264 ms, faster than 58.33% of JavaScript online submissions for Number of Recent Calls.
#### Memory Usage: 56.1 MB, less than 100.00% of JavaScript online submissions for Number of Recent Calls.
=======
#========
# Runtime: 264 ms, faster than 58.33% of JavaScript online submissions for Number of Recent Calls.
# Memory Usage: 56.1 MB, less than 100.00% of JavaScript online submissions for Number of Recent Calls.
>>>>>>> 4dfa857... rename test
```
var RecentCounter = function() {
    this.q = [];
};

/** 
 * @param {number} t
 * @return {number}
 */
RecentCounter.prototype.ping = function(t) {
    this.q.push(t);
    while(this.q[0] < t - 3000){
        this.q.shift();
    }
    return this.q.length;
};

/** 
 * Your RecentCounter object will be instantiated and called as such:
 * var obj = new RecentCounter()
 * var param_1 = obj.ping(t)
 */
```
