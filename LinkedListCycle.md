141. Linked List Cycle
https://leetcode.com/problems/linked-list-cycle/description/


PYTHON SOLUTION #1:
Using HashSet.
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        
        l = set()

        while head:

            if head in l:
                return True
            
            l.add(head)
            head = head.next


        return False
```



PYTHON SOLUTION #2:
Using Floyd's algotithm(slow-fast)
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        
        l = set()

        while head:

            if head in l:
                return True
            
            l.add(head)
            head = head.next

            

        return False
```

