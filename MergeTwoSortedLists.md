21. Merge Two Sorted Lists
https://leetcode.com/problems/merge-two-sorted-lists/description/?envType=problem-list-v2&envId=linked-list&difficulty=EASY


PYTHON SOLUTION:

# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:

        dummy = ListNode(0)
        current = dummy

        
        while list1 and list2:

            if list1.val < list2.val:
                rez = list1.val if list1 else 0
                list1 = list1.next
                current.next = ListNode(rez)
            elif list1.val > list2.val:
                rez = list2.val if list2 else 0
                list2 = list2.next
                current.next = ListNode(rez)
            else:
                if list1 and list2:
                    current.next = ListNode(list1.val)
                    current = current.next
                    current.next = ListNode(list2.val)
                    list1 = list1.next
                    list2 = list2.next
                elif not list1 and list2:
                    rez = list1.val
                    list1 = list1.next
                    current.next = ListNode(rez)
                else:
                    rez = list2.val
                    list2 = list2.next
                    current.next = ListNode(rez)
            current = current.next

        if list1:
            while list1:
                current.next = ListNode(list1.val) if list1 else 0 
                current = current.next
                list1 = list1.next
        elif list2:
            while list2:
                current.next = ListNode(list2.val) if list2 else 0 
                current = current.next
                list2 = list2.next
                
        return dummy.next
