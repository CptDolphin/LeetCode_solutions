2. Add Two Numbers
Medium

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example:

Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
Explanation: 342 + 465 = 807.

Accepted
1,140,976
Submissions
3,521,874

---
#### Not solved yet - to be continued;
```javascript
var addTwoNumbers = function(l1, l2) {
    let total = 0;
    
    let prev = null;
    let temp = null;
    let split_prev = null;
    
    [l1, l2].forEach(num => {
        while(num){
            temp = num.next;
            num.next = prev;
            prev = num;
            num = temp;
        }
        
        while(prev){
            total += prev.val;
            split_prev = prev;
            prev = prev.next;
        }
    });
    
    return total;
};
```


---
```javascript
// Not finished yet missing few ifs at the end
var addTwoNumbers = function(l1, l2) {
    let result = new ListNode(null);
    let head = result;
    let node = new ListNode(null);
    let sum = 0;
    var temp = null;
    let next = 0;
    

    l1 = reverse(l1);
    l2 = reverse(l2);

    
    while(l1 && l2){
        sum = l1.val + l2.val;
        if(sum > 9){
            temp = sum/10;
            sum %= 10;
        }
        
        node = new ListNode(sum + next);
        next = temp;
        
        head.next = node;
        head = head.next;
        
        l1 = l1.next;
        l2 = l2.next;
    }

    return result.next;
};

function reverse(l){
    let prev = null;
    while(l){
        temp = l.next;
        l.next = prev;
        prev = l;
        l = temp;
    }
    
    return prev;
}
```

