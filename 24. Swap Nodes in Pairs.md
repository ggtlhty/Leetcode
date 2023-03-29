**24. Swap Nodes in Pairs**

Given a linked list, swap every two adjacent nodes and return its head. You must solve the problem without modifying the values in the list's nodes (i.e., only nodes themselves may be changed.)


**Example 1:**

![example](https://assets.leetcode.com/uploads/2020/10/03/swap_ex1.jpg)


```
Input: head = [1,2,3,4]
Output: [2,1,4,3]
```
**Example 2:**
```
Input: head = []
Output: []
```
**Example 3:**

```
Input: head = [1]
Output: [1]
```
**Constraints:**
```
The number of nodes in the list is in the range [0, 100].
0 <= Node.val <= 100
```

**Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def swapPairs(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """

        new_node = ListNode()
        new_node.next = head

        c = new_node

        while c.next and c.next.next:
            temp1 = c.next
            temp2 = c.next.next.next
            c.next = c.next.next
            c.next.next = temp1
            c.next.next.next = temp2
            c = c.next.next

        return new_node.next

```
