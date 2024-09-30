268. Missing Number
https://leetcode.com/problems/missing-number/description/?envType=problem-list-v2&envId=binary-search&difficulty=EASY

PYTHON SOLUTION #1:

```
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        
        rez = 0 

        def binarysearch(arr, st, end, x):

            while st <= end:

                mid = st + (end - st)//2
                if arr[mid] == x:
                    return True
                elif arr[mid] < x:
                    st = mid + 1
                else:
                    end = mid - 1
                
            return False
        
        nums.sort()
        
        for i in range(len(nums) + 1):

            if not binarysearch(nums, 0, len(nums) - 1, i):
                rez = i
        
        return rez


```

PYTHON SOLUTION #2:

```
class Solution:
    def missingNumber(self, nums: List[int]) -> int:

        s1 = len(nums)*(len(nums)+1)//2
        s2 = sum(nums)
        return s1 - s2

```
