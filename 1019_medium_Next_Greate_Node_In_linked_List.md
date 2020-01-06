# 1019. Next Greater Node In Linked List
Medium

We are given a linked list with head as the first node.  Let's number the nodes in the list: node_1, node_2, node_3, ... etc.

Each node may have a next larger value: for node_i, next_larger(node_i) is the node_j.val such that j > i, node_j.val > node_i.val, and j is the smallest possible choice.  If such a j does not exist, the next larger value is 0.

Return an array of integers answer, where answer[i] = next_larger(node_{i+1}).

Note that in the example inputs (not outputs) below, arrays such as [2,1,5] represent the serialization of a linked list with a head node value of 2, second node value of 1, and third node value of 5.

 

Example 1:

Input: [2,1,5]
Output: [5,5,0]

Example 2:

Input: [2,7,4,3,5]
Output: [7,0,5,5,0]

Example 3:

Input: [1,7,5,1,9,2,5,1]
Output: [7,9,9,9,0,5,0,0]

 

Note:

    1 <= node.val <= 10^9 for each node in the linked list.
    The given list has length in the range [0, 10000].

---
#### Runtime: 1352 ms, faster than 36.59% of JavaScript online submissions for Next Greater Node In Linked List.
#### Memory Usage: 79.8 MB, less than 100.00% of JavaScript online submissions for Next Greater Node In Linked List.
```javascript
var nextLargerNodes = function(head) {
    if(head == null || head.next == null){
        return [0];
    }
    
    const result = [];
    let count = 0;
    
    while(head){
        result[count++] = head.val;
        head = head.next;
    }
    
    return result.map((num, i) => result.slice(i+1).find(elem => elem > num) || 0);
};
```
---
#### Runtime: 136 ms, faster than 98.37% of JavaScript online submissions for Next Greater Node In Linked List.
#### Memory Usage: 43.2 MB, less than 100.00% of JavaScript online submissions for Next Greater Node In Linked List.
```javascript
var nextLargerNodes = function(head) {
    let count = 0;
    let prev = null;
    let temp = null;
    
    // Reverse Linked List and count it's length
    while(head){
        count++;
        temp = head.next;
        head.next = prev;
        prev = head;
        head = temp;
    }
    
    // Create new Array with Length of Linked List
    const result = new Array(count).fill(0);
    let iter = count - 1;
    let stack = null;
    
    // Reverse once again
    while(prev){
        temp = prev;
        prev = prev.next;
        while(stack && stack.val <= temp.val){
            stack = stack.next;
        }
        
        if(stack){
            result[iter] = stack.val;
        }
        
        iter -= 1;
        temp.next = stack;
        stack = temp;
    }
    
    return result;
};
```
