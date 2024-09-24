206. Reverse Linked List
https://leetcode.com/problems/reverse-linked-list/description/

PYTHON SOLUTION #1:
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
    
        prev = None

        current = head

        while current:

            next = current.next
            current.next = prev

            prev = current
            current = next
        
        return prev
```

PYTHON SOLUTION #2:

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        l = []

        while head:

            l.append(head.val)
            head = head.next
        
        dummy = ListNode(0)
        current = dummy

        l.reverse()

        for i in range(len(l)):

            current.next = ListNode(l[i])
            current = current.next

        return dummy.next
```
