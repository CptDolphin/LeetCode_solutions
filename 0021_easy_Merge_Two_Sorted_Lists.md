# 21. Merge Two Sorted Lists
Easy

3115

457

Add to List

Share
Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.

Example:

Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4

---
#### Runtime: 68 ms, faster than 47.75% of JavaScript online submissions for Merge Two Sorted Lists.
#### Memory Usage: 36 MB, less than 20.51% of JavaScript online submissions for Merge Two Sorted Lists.
```javascript
var mergeTwoLists = function(l1, l2) {
    if(l1 == null) {
        return l2;
    }
    
    if(l2 == null) {
        return l1;
    }
    
    let temp = null;
    let prev = null;
    let result = null;
    let final = null;
    
    while(l1 || l2){
        if(l1 && l2){
            if(l1.val <= l2.val){
                temp = l1.next;
                l1.next = result;
                result = l1;
                l1 = temp;

            } else {
                temp = l2.next;
                l2.next = result;
                result = l2;
                l2 = temp;
            }
        } else if (l2) {
            temp = l2.next;
            l2.next = result;
            result = l2;
            l2 = temp;
        } else if (l1) {
            temp = l1.next;
            l1.next = result;
            result = l1;
            l1 = temp;
        }
    }
    
    while(result){
        temp = result.next;
        result.next = final;
        final = result;
        result = temp;
    }
    
    return final;
};
```
---
#### Runtime: 76 ms, faster than 18.09% of JavaScript online submissions for Merge Two Sorted Lists.
#### Memory Usage: 35.7 MB, less than 28.21% of JavaScript online submissions for Merge Two Sorted Lists.
```javascript
var mergeTwoLists = function(l1, l2) {
    var head = new ListNode(null);
    var temp = head;
    
    while(l1 != null && l2 != null) {

        if(l1.val <= l2.val) {
            temp.next = new ListNode(l1.val);
            l1 = l1.next;
        } else {
            temp.next = new ListNode(l2.val);
            l2 = l2.next;
        }
        
        dtemp= temp.next;
    }
    
    temp.next = (l1 == null) ? l2 : l1;
    
    return head.next;
};
```
