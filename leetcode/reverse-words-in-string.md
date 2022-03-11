**Problem Statement**
Given a string s, reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

 
**Examples**
Example 1:
```js
Input: s = "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"
```

Example 2:
```js
Input: s = "God Ding"
Output: "doG gniD"
```

Constraints:
```js
1 <= s.length <= 5 * 104
s contains printable ASCII characters.
s does not contain any leading or trailing spaces.
There is at least one word in s.
All the words in s are separated by a single space.
```

**Solution**
```js
const reverseWords = (s) => {
    return s.split(" ").map( el => el.split("").reverse().join("")).join(" ").trim();
};
```

**Reference:**
https://leetcode.com/problems/reverse-words-in-a-string-iii/
