**1047. Remove All Adjacent Duplicates In String**

You are given a string s consisting of lowercase English letters. A duplicate removal consists of choosing two adjacent and equal letters and removing them.

We repeatedly make duplicate removals on s until we no longer can.

Return the final string after all such duplicate removals have been made. It can be proven that the answer is unique.

**Example 1:**


```
Input: s = "abbaca"
Output: "ca"
Explanation: 
For example, in "abbaca" we could remove "bb" since the letters are adjacent and equal, and this is the only possible move.  The result of this move is that the string is "aaca", of which only "aa" is possible, so the final string is "ca".
```
**Example 2:**

```
Input: s = "azxxzy"
Output: "ay"
```

**Constraints:**

```
1 <= s.length <= 105
s consists of lowercase English letters.
```

**Solution:**

Python
```python
class Solution(object):
    def removeDuplicates(self, s):
        """
        :type s: str
        :rtype: str
        """

        stack = []

        for i in s:
            if stack and i == stack[-1]:
                stack.pop()
                
            else:
                 stack.append(i)

        return ''.join(stack)

```
C++
```cpp
class Solution {
public:
    string removeDuplicates(string s) {
        
        string res;
        for (char i:s){
            if (not res.empty() and res.back() == i){
                res.pop_back();
            }
            else{
                res.push_back(i);
            }
        }
        
        return res;
    }
};

```
