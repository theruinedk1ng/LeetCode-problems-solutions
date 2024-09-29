287. Find the Duplicate Number
https://leetcode.com/problems/find-the-duplicate-number/description/


PYTHON SOLUTION #1:

```
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:

        nums.sort()
        
        def binarysearch(arr, st, end, x, y):

            while st <= end:

                mid = st + (end - st)//2
                if arr[mid] == x and mid != i:
                    return True
                elif arr[mid] < x:
                    st = mid + 1
                else:
                    end = mid - 1

            return False


        for i in range(len(nums)):
            if binarysearch(nums, 0, len(nums)-1, nums[i], i):
                rez = nums[i]

        return rez
```

PYTHON SOLUTION #2:

```
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
        
        slow = nums[0]
        fast = nums[0]

        while True:

            slow = nums[slow]
            fast = nums[nums[fast]]
            if slow == fast:
                break

        fast = nums[0]

        while fast != slow:
            
            slow = nums[slow]
            fast = nums[fast]

        return slow
```
