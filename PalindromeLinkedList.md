234. Palindrome Linked List
https://leetcode.com/problems/palindrome-linked-list/description/


PYTHON SOLUTION:

```
  # Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def isPalindrome(self, head: Optional[ListNode]) -> bool:
        
        l = []

        while head:

            l.append(head.val)
            head = head.next
        
        if len(l) == 1:
            return True
        

        if len(l) % 2 != 0:
            
            st = 0 
            end = len(l) - 1

            while st != end:

                if l[st] != l[end]:
                    return False
                st += 1
                end -= 1
        else:

            st = 0 
            end = len(l)

            while st != len(l)//2  and end != len(l)//2:
                         
                if l[st] != l[end-1]:
                    return False
                st += 1
                end -= 1


        return True
