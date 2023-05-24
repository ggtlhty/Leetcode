**977. Squares of a Sorted Array**


Given an integer array nums sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.

**Example 1:**

Input: nums = [-4,-1,0,3,10]
Output: [0,1,9,16,100]
Explanation: After squaring, the array becomes [16,1,0,9,100].
After sorting, it becomes [0,1,9,16,100].

**Example 2:**

Input: nums = [-7,-3,2,3,11]
Output: [4,9,9,49,121]
 

**Constraints:**
```
1 <= nums.length <= 104
-104 <= nums[i] <= 104
nums is sorted in non-decreasing order.
```

**Solution:**
```python
class Solution(object):
    def sortedSquares(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """

        a, b = 0, len(nums)-1
        new=nums[:]
        l = b
        while a<=b:
            if nums[a]*nums[a]>= nums[b]*nums[b]:
                new[l]=nums[a]*nums[a]
                a+=1
                l-=1
            else:
                new[l]=nums[b]*nums[b]
                b-=1
                l-=1
        
        return new
```
