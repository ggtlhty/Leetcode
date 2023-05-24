**20. Valid Parentheses**

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.

**Example 1:**


```
Input: s = "()"
Output: true
```
**Example 2:**

```
Input: s = "()[]{}"
Output: true
```
**Example 3:**

```
Input: s = "(]"
Output: false
```
**Constraints:**

```
1 <= s.length <= 104
s consists of parentheses only '()[]{}'.
```

**Solution:**

Python
```python
class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        d =  {'(':')', '{':'}','[':']'}
        stack = []

        for i in s:
            if i in ['(','[','{']:
                stack.append(d[i])
            elif not stack or stack[-1]!=i:
                return False
            else:
                stack.pop()

        return stack==[]
            

```
C++
```cpp
class Solution {
public:
    bool isValid(string s) {
        if (s.size()%2 == 1){
            return false;
        }

        stack<char> stk;
        for (int i =0;i<s.size();i++){
            if (s[i] == '(') stk.push(')');
            else if (s[i] == '[') stk.push(']');
            else if (s[i] == '{') stk.push('}');

            else if (stk.empty() or stk.top()!= s[i]){
                return false;
            }
            else{
                stk.pop();
            }
        }
        return stk.empty();
    }
};

```
