# 83. Remove Duplicates from Sorted List
Easy

Given a sorted linked list, delete all duplicates such that each element appear only once.

Example 1:

Input: 1->1->2
Output: 1->2

Example 2:

Input: 1->1->2->3->3
Output: 1->2->3

---
#### Runtime: 72 ms, faster than 42.36% of JavaScript online submissions for Remove Duplicates from Sorted List.
#### Memory Usage: 35.5 MB, less than 93.75% of JavaScript online submissions for Remove Duplicates from Sorted List.
```javascript
var deleteDuplicates = function(head) {
    let node = head;
    
    while(node !== null && node.next !== null){
        while(node !== null && node.next !== null && node.val === node.next.val){
            node.next = node.next.next;
        }
        node = node.next;
    }
    
    return head;
};
```
---
#### Runtime: 60 ms, faster than 93.47% of JavaScript online submissions for Remove Duplicates from Sorted List.
#### Memory Usage: 35.5 MB, less than 93.75% of JavaScript online submissions for Remove Duplicates from Sorted List.
```javascript
var deleteDuplicates = function(head) {
    let node = head;
    
    while(node !== null && node.next !== null){
        if(node.val === node.next.val){
            node.next = node.next.next;
        } else {
            node = node.next;
        }
    }
    
    return head;
};
```
