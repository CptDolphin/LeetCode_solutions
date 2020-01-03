938. Range Sum of BST
Easy

Given the root node of a binary search tree, return the sum of values of all nodes with value between L and R (inclusive).

The binary search tree is guaranteed to have unique values.

 

Example 1:

Input: root = [10,5,15,3,7,null,18], L = 7, R = 15
Output: 32

Example 2:

Input: root = [10,5,15,3,7,13,18,1,null,6], L = 6, R = 10
Output: 23

 

Note:

    The number of nodes in the tree is at most 10000.
    The final answer is guaranteed to be less than 2^31.


---
#### Runtime: 160 ms, faster than 83.10% of JavaScript online submissions for Range Sum of BST.
#### Memory Usage: 67 MB, less than 69.23% of JavaScript online submissions for Range Sum of BST.
#### Recursive
```javascript
var rangeSumBST = function(root, L, R) {
    if(root == null || L == null || R == null) {
        return 0;
    }
    
    if(!root.left && !root.right) {
        return root.val;
    }
    
    return helper(root, L, R);
};

function helper(root, L, R, total = 0){
    if(root == null) {
        return total;
    }
    
    total += helper(root.left, L, R) + helper(root.right, L, R);
    
    if(root.val >= L && root.val <= R) {
        total += root.val;
    }

    if(root.val > R) {
        return total;
    }
    
    return total; 
}
```
---
#### Runtime: 164 ms, faster than 68.95% of JavaScript online submissions for Range Sum of BST.
#### Memory Usage: 71.2 MB, less than 11.54% of JavaScript online submissions for Range Sum of BST.
#### Iterative
```javascript
var rangeSumBST = function(root, L, R) {
    if(root == null || L == null || R == null){
        return 0;
    }
    
    if(!root.left && !root.right){
        return root.val;
    }
    
    let result = 0;
    const stack = [];
    let node = root;
    
    while(stack.length > 0 || node){
        if(node){    
            stack.push(node);
            node = node.left;
        } else { 
            node = stack.pop();

            if(node.val >= L && node.val <= R){
                result += node.val;
            } 

            if(node. val >= R){
                break;
            }
        
            node = node.right;
        }
    }
    
    return result;
};
```
---

