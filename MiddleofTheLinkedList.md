876. Middle of the Linked List
https://leetcode.com/problems/middle-of-the-linked-list/description/

PYTHON SOLUTION

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        l = []

        dummy = ListNode(0)
        current = dummy

        while head:

            l.append(head.val)
            head = head.next
        
        for i in range(len(l)//2, len(l)):

            current.next = ListNode(l[i])
            current = current.next

        return dummy.next

```
