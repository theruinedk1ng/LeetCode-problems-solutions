83. Remove Duplicates from Sorted List
https://leetcode.com/problems/remove-duplicates-from-sorted-list/description/


PYTHON SOLUTION #1:
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:

        current = head

        while current:

            while current.next and current.next.val == current.val:
                current.next = current.next.next
            current = current.next

        return head
```
        

PYTHON SOLUTION #2:

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:

        prev = -111
        dummy = ListNode(0)
        current = dummy

        while head:

            if head.val != prev:
                prev = head.val 
                current.next = ListNode(prev)
                current = current.next
             
            head = head.next
        
        return dummy.next

```


