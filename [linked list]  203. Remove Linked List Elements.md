**203. Remove Linked List Elements**

Given the head of a linked list and an integer val, remove all the nodes of the linked list that has Node.val == val, and return the new head.

 ![example](https://assets.leetcode.com/uploads/2021/03/06/removelinked-list.jpg)
**Example 1:**
```
Input: head = [1,2,6,3,4,5,6], val = 6
Output: [1,2,3,4,5]
```
**Example 2:**
```
Input: head = [], val = 1
Output: []
```
**Example 3:**
```
Input: head = [7,7,7,7], val = 7
Output: []
```
**Constraints:**
```
The number of nodes in the list is in the range [0, 104].
1 <= Node.val <= 50
0 <= val <= 50
```

**Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def removeElements(self, head, val):
        """
        :type head: ListNode
        :type val: int
        :rtype: ListNode
        """
        
        
        while head and head.val == val:
            
            if head.next == None:
                return None
            else:
                head = head.next
            
        a = head
        '''
        while a:

            if a.val == val:
                tmp.next = a.next
            else:
                tmp = a
            a=a.next
        '''

        while a and a.next:
            if a.next.val == val:
                a.next = a.next.next
            else:
                a=a.next
            
        return head


```
