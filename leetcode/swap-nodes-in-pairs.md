**Problem Statement**
Given a linked list, swap every two adjacent nodes and return its head. You must solve the problem without modifying the values in the list's nodes (i.e., only nodes themselves may be changed.)

 
**Examples**
Example 1:

![Swap nodes in pairs](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/omafrxw826vt461suq98.jpeg)
```js
Input: head = [1,2,3,4]
Output: [2,1,4,3]
```

Example 2:
```js
Input: head = []
Output: []
```

Example 3:
```js
Input: head = [1]
Output: [1]
```

**Constraints:**
```js
The number of nodes in the list is in the range [0, 100].
0 <= Node.val <= 100
```

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
 * @param {ListNode} head
 * @return {ListNode}
 */
const swapPairs = (n) => {
    if (n === null) {
        return null
    }
    if (n.next === null) {
        return n
    }
    let n1 = n.next
    let n2 = n.next.next
    n1.next = n
    n.next = swapPairs(n2)
    return n1
};
```
**LeetCode issue:** 
https://leetcode.com/problems/swap-nodes-in-pairs/

[How to implement a Linked List?](https://www.freecodecamp.org/news/implementing-a-linked-list-in-javascript/)
