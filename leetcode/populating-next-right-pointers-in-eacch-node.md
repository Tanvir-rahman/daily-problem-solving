**Problem Statement**
You are given a perfect binary tree where all leaves are on the same level, and every parent has two children. The binary tree has the following definition:

```js
struct Node {
  int val;
  Node *left;
  Node *right;
  Node *next;
}
```

Populate each next pointer to point to its next right node. If there is no next right node, the next pointer should be set to `NULL`

Initially, all next pointers are set to `NULL`.

 
**Examples**
Example 1:
![Problem Statement](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/n3bm0s5ng71wykpumre6.png)

```js
Input: root = [1,2,3,4,5,6,7]
Output: [1,#,2,3,#,4,5,6,7,#]
Explanation: Given the above perfect binary tree (Figure A), your function should populate each next pointer to point to its next right node, just like in Figure B. The serialized output is in level order as connected by the next pointers, with '#' signifying the end of each level.
```

Example 2:
```js
Input: root = []
Output: []
```

**Constraints:**
```js
nums1.length == m
nums2.length == n
0 <= m <= 1000
0 <= n <= 1000
1 <= m + n <= 2000
-106 <= nums1[i], nums2[i] <= 106
```

**Solution**
```js
const connect = (root) => {
    if(!root) return root;
    let q = [root];
    
    while(q.length){
        const temp = [];
        for(let i = 0; i < q.length; i++){
            const n = q[i];
            
            n.next = q[i+1] || null;
            if(n.left){
                temp.push(n.left);
                temp.push(n.right);
            }
        }
        q = temp;
    }
    
    return root;
};
```
**LeetCode issue:** 
https://leetcode.com/problems/populating-next-right-pointers-in-each-node/
