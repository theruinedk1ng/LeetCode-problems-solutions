92. Reverse Linked List II
https://leetcode.com/problems/reverse-linked-list-ii/description/

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseBetween(self, head: Optional[ListNode], left: int, right: int) -> Optional[ListNode]:
        

        if not head or right == left:
            return head
        l = []
        rez = []
        k = False
        dummy = ListNode(0)
        current = dummy

        while head:

            l.append(head.val)
            head = head.next
        
        for i in range(len(l)):
            
            if i == left - 1:
                k = True
            if i == right - 1:
                k = False
            
            if k:
                rez.append(l[i])
            if not k and i == right - 1:
                rez.append(l[i])
        var = 0
        rez.reverse()
        k = False
        for i in range(len(l)):

            if i == left - 1:
                k = True
            if i == right - 1:
                k = False
            
            if not k and i != right - 1:
                current.next = ListNode(l[i])
                current = current.next
            if k and var == 0:
                for j in range(len(rez)):
                    var = 1
                    current.next = ListNode(rez[j])
                    current = current.next
        


        return dummy.next

```
