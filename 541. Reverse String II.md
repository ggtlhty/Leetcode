**541. Reverse String II**

Given a string s and an integer k, reverse the first k characters for every 2k characters counting from the start of the string.

If there are fewer than k characters left, reverse all of them. If there are less than 2k but greater than or equal to k characters, then reverse the first k characters and leave the other as original.

 


**Example 1:**


```
Input: s = "abcdefg", k = 2
Output: "bacdfeg"
```
**Example 2:**

```
Input: s = "abcd", k = 2
Output: "bacd"
```

**Constraints:**

```
1 <= s.length <= 104
s consists of only lowercase English letters.
1 <= k <= 104
```

**Solution:**

Python
```python
class Solution(object):
    def reverseStr(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: str
        """
        def reverse_substring(text):
            left, right = 0, len(text)-1
            while left < right:
                text[left], text[right] = text[right], text[left]
                left += 1
                right -= 1
            return text

        res = list(s)
        for i in range(0, len(s), 2*k):
            res[i:i+k] = reverse_substring(res[i:i+k])
        
        return ''.join(res)

```
C++
```cpp
class Solution {
public:
    string reverseStr(string s, int k) {
        for(int i = 0; i < s.size(); i += 2*k){
            if((i + k) <= s.size()){
                reverse(s.begin() + i, s.begin() + i + k);
            }
            else{
                reverse(s.begin() + i, s.end());
            }
        }
        return s;
    }
};

```
