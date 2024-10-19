4. Median of Two Sorted Arrays
https://leetcode.com/problems/median-of-two-sorted-arrays/description/


PYTHON SOLUTION

```
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:

        l = []

        for i in nums1:
            l.append(i)
        
        for i in nums2:
            l.append(i)
        
        l.sort()

        if len(l) % 2 != 0:
            return l[len(l)//2]
            
        return (l[len(l)//2] + l[len(l)//2 - 1])/2
        
        
        
```
