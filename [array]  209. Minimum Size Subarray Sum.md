**209. Minimum Size Subarray Sum**

Given an array of positive integers nums and a positive integer target, return the minimal length of a 
subarray whose sum is greater than or equal to target. If there is no such subarray, return 0 instead.
 
**Example 1:**
```
Input: target = 7, nums = [2,3,1,2,4,3]
Output: 2
Explanation: The subarray [4,3] has the minimal length under the problem constraint.
```
**Example 2:**
```
Input: target = 4, nums = [1,4,4]
Output: 1
```
**Example 3:**
```
Input: target = 11, nums = [1,1,1,1,1,1,1,1]
Output: 0
```
**Constraints:**
```
1 <= target <= 109
1 <= nums.length <= 105
1 <= nums[i] <= 104
```

**Solution:**
```python
class Solution(object):
    def minSubArrayLen(self, target, nums):
        """
        :type target: int
        :type nums: List[int]
        :rtype: int
        """

        i = 0
        s = 0
        
        m = float("inf")
        for j in range(0,len(nums)):
            s+=nums[j]
            
            while s>=target:
                m = min(m,j-i+1)
                
                s-=nums[i]
                i+=1
                
        return 0 if m == float("inf") else m

```
