# 206. Reverse Linked List
Easy

3220

77

Add to List

Share
Reverse a singly linked list.

Example:

Input: 1->2->3->4->5->NULL
Output: 5->4->3->2->1->NULL
Follow up:

A linked list can be reversed either iteratively or recursively. Could you implement both?

---
#### Runtime: 52 ms, faster than 94.88% of JavaScript online submissions for Reverse Linked List.
#### Memory Usage: 35.2 MB, less than 45.65% of JavaScript online submissions for Reverse Linked List.

```javascript
var reverseList = function(head) {
    let node = head;
    let prev = null;
    let temp = new ListNode();
    
    while(node){
        temp = node.next;
        node.next = prev;
        prev = node;
        node = temp;
    }
    
    return prev;
};
```
---
#### Runtime: 48 ms, faster than 98.99% of JavaScript online submissions for Reverse Linked List.
#### Memory Usage: 35.3 MB, less than 34.78% of JavaScript online submissions for Reverse Linked List.
```javascript
var reverseList = function(head) {
   if(!head || !head.next){
       return head;
   }
    let temp = reverseList(head.next);
    head.next.next = head;
    head.next = undefined;
    return temp;
};
```
