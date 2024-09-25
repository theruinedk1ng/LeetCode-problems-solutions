1290. Convert Binary Number in a Linked List to Integer
https://leetcode.com/problems/convert-binary-number-in-a-linked-list-to-integer/description/


PYTHON SOLUTION

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def getDecimalValue(self, head: ListNode) -> int:

        rez = ''

        while head:

            rez = rez + str(head.val)

            head = head.next
        
        rez = int(rez, 2)
        
        return rez
```
        
