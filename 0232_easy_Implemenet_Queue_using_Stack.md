# 232. Implement Queue using Stacks
Easy

Implement the following operations of a queue using stacks.

    push(x) -- Push element x to the back of queue.
    pop() -- Removes the element from in front of queue.
    peek() -- Get the front element.
    empty() -- Return whether the queue is empty.

Example:

MyQueue queue = new MyQueue();

queue.push(1);
queue.push(2);  
queue.peek();  // returns 1
queue.pop();   // returns 1
queue.empty(); // returns false

Notes:

    You must use only standard operations of a stack -- which means only push to top, peek/pop from top, size, and is empty operations are valid.
    Depending on your language, stack may not be supported natively. You may simulate a stack by using a list or deque (double-ended queue), as long as you use only standard operations of a stack.
    You may assume that all operations are valid (for example, no pop or peek operations will be called on an empty queue).

---

## These tests are pretty unreliable as they vary +- 10-30ms all the time, only indicator if you did well is 50vs150vs250vs1500ms

#### Runtime: 68 ms, faster than 8.55% of JavaScript online submissions for Implement Queue using Stacks.
#### Memory Usage: 33.7 MB, less than 100.00% of JavaScript online submissions for Implement Queue using Stacks.

#### Runtime: 40 ms, faster than 99.76% of JavaScript online submissions for Implement Queue using Stacks.
#### Memory Usage: 33.8 MB, less than 33.33% of JavaScript online submissions for Implement Queue using Stacks.

```javascript
var MyQueue = function() {
    this.que = [];
};

/**
 * Push element x to the back of queue. 
 * @param {number} x
 * @return {void}
 */
MyQueue.prototype.push = function(x) {
    this.que.push(x);
};

/**
 * Removes the element from in front of queue and returns that element.
 * @return {number}
 */
MyQueue.prototype.pop = function() {
    return this.que.shift();
};

/**
 * Get the front element.
 * @return {number}
 */
MyQueue.prototype.peek = function() {
    if(this.que.length > 0){
        return this.que[0];
    } else {
        return null;
    }
};

/**
 * Returns whether the queue is empty.
 * @return {boolean}
 */
MyQueue.prototype.empty = function() {
    return this.que.length === 0;
};
```
