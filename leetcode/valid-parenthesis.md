**Problem Statement**
Given a string s containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
 
**Examples**
Example 1:
```js
Input: s = "()"
Output: true
```

Example 2:
```js
Input: s = "()[]{}"
Output: true
```

Example 3:
```js
Input: s = "(]"
Output: false
```

**Constraints:**
```js
1 <= s.length <= 104
s consists of parentheses only '()[]{}'.
```

**Solution**
```js
const isValid = (s) => {
    if (s.length <=1) return false;
    
    const stack = []
    const hash = {
        '(' : ')',
        '[' : ']',
        '{' : '}'
    }
    
    for(let i = 0; i < s.length; i++){
        if (hash[s[i]]) stack.push(hash[s[i]])
        else if (s[i] !== stack.pop()) return false
    }
    return !stack.length
};
```

**LeetCode issue:** 
https://leetcode.com/problems/valid-parentheses/
