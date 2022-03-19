**Problem Statement**
You are given two **non-empty** linked lists representing two non-negative integers. The digits are stored in **reverse order**, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.
 
**Examples**
Example 1:
![add two numbers](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/w481twxvdj4i86jw97d0.jpeg)
```js
Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.
```

Example 2:
```js
Input: l1 = [0], l2 = [0]
Output: [0]
```

Example 3:
```js
Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
Output: [8,9,9,9,0,0,0,1]
```

**Constraints:**
- The number of nodes in each linked list is in the range [1, 100].
- `0 <= Node.val <= 9`
- It is guaranteed that the list represents a number that does not have leading zeros.

**Solution**
```js
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var addTwoNumbers = function(l1, l2) {
    if (l1 == null && l2 == null) return 0;
    let dummie = new ListNode();
    let node = dummie;
    let carrier = false;
    while (l1 || l2 || carrier) {
        let new_value = 0;
		// sum nodes if availible
        if (l1) [new_value, l1] = [new_value + l1.val, l1.next];
        if (l2) [new_value, l2] = [new_value + l2.val, l2.next];
        // take care of the carrier
        if (carrier) [new_value, carrier] = [new_value + 1, false];
        if (new_value >= 10) carrier = true;
        // append new node
        node.next = new ListNode(new_value % 10);
        node = node.next;
    }
    return dummie.next;
};
```
**LeetCode issue:** 
https://leetcode.com/problems/add-two-numbers/
