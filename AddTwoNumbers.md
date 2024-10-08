2. Add Two Numbers
https://leetcode.com/problems/add-two-numbers/description/

PYTHON SOLUTION

```
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        p1 = []
        p2 = []
        
   
        while l1:
            p1.append(l1.val)
            l1 = l1.next
        while l2:
            p2.append(l2.val)
            l2 = l2.next
        
   
        rez = ListNode(0)
        current = rez
        carry = 0
        

        m = len(p1)
        n = len(p2)
        
  
        for i in range(min(m, n)):
            total = p1[i] + p2[i] + carry
            carry = total // 10  
            current.next = ListNode(total % 10)
            current = current.next
        
        for i in range(min(m, n), m):
            total = p1[i] + carry
            carry = total // 10
            current.next = ListNode(total % 10)
            current = current.next
        
        for i in range(min(m, n), n):
            total = p2[i] + carry
            carry = total // 10
            current.next = ListNode(total % 10)
            current = current.next
        

        if carry:
            current.next = ListNode(carry)
        
        return rez.next  

```
