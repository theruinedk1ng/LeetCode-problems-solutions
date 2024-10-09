82. Remove Duplicates from Sorted List II
https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/description/


PYTHON SOLUTION

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        l = []
        mp = {}
        dummy = ListNode(0)
        current = dummy


        while head:

            l.append(head.val)
            head = head.next
        
        for i in range(len(l)):

            if l[i] not in mp:
                mp[l[i]] = 1
            else:
                mp[l[i]] += 1
        
        for i in range(len(l)):

            if mp[l[i]] == 1:
                current.next = ListNode(l[i])
                current = current.next
        
        
        return dummy.next
```
