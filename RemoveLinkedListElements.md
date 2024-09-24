203. Remove Linked List Elements
https://leetcode.com/problems/remove-linked-list-elements/description/

PYTHON SOLUTION #1:
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeElements(self, head: Optional[ListNode], val: int) -> Optional[ListNode]:
        

        prev = None
        current = head

        while current:

            if current.val == val:
                if prev:
                    prev.next = current.next
                else:
                    head = current.next
                current = current.next
            else:
                prev = current
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
    def removeElements(self, head: Optional[ListNode], val: int) -> Optional[ListNode]:
        
        dummy = ListNode(0)
        current = dummy

        while head:

            if head.val != val:

                current.next = ListNode(head.val)
                current = current.next

            head = head.next

        return dummy.next
```

