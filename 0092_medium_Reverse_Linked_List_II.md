# 92. Reverse Linked List II
Medium

Reverse a linked list from position m to n. Do it in one-pass.

Note: 1 ≤ m ≤ n ≤ length of list.

Example:

Input: 1->2->3->4->5->NULL, m = 2, n = 4
Output: 1->4->3->2->5->NULL

---
#### Runtime: 52 ms, faster than 82.23% of JavaScript online submissions for Reverse Linked List II.
#### Memory Usage: 33.8 MB, less than 42.86% of JavaScript online submissions for Reverse Linked List II.

```javascript
var reverseBetween = function(head, m, n) {
    if(m === n){
        return head;
    }
    
    let prev = null;
    let curr = head;
    let count = 0;
    let first = null;
    let split_prev = null;
    let next = null;
    
    while(count <= n){
        if(++count < m){
            prev = curr;
            curr = curr.next;
        }
        
        if(count === m){
            first = curr;
            split_prev = curr;
            curr = curr.next;
        }
        
        if(count > m && count <= n){
            next = curr.next;
            curr.next = split_prev;
            split_prev = curr;
            curr = next;            
        }
    }
    
    first.next = next;
    
    if(prev){
        prev.next = split_prev;
    }
    
    if(m > 1){
        return head;
    }
    
    return split_prev;
};
```
