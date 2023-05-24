**206. Reverse Linked List**

Given the head of a singly linked list, reverse the list, and return the reversed list.



**Example 1:**

![example](https://assets.leetcode.com/uploads/2021/02/19/rev1ex1.jpg)
```
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]
```

**Example 2:**

![example](https://assets.leetcode.com/uploads/2021/02/19/rev1ex2.jpg)
```
Input: head = [1,2]
Output: [2,1]
```
**Example 3:**
```
Input: head = []
Output: []
```
**Constraints:**
```
The number of nodes in the list is the range [0, 5000].
-5000 <= Node.val <= 5000
```

**Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def reverseList(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        c = head
        prev = None

        while c:
            temp = c.next
            c.next = prev
            prev = c
            c = temp
        return prev

```
