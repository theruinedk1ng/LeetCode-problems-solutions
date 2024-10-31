2420. Find All Good Indices
https://leetcode.com/problems/find-all-good-indices/description/

PYTHON SOLUTION  
```
class Solution:
    def goodIndices(self, nums: List[int], k: int) -> List[int]:
        n = len(nums)
        if n < 2 * k + 1:
            return []  

        non_increasing = [1] * n
        for i in range(1, n):
            if nums[i] <= nums[i - 1]:
                non_increasing[i] = non_increasing[i - 1] + 1

        non_decreasing = [1] * n
        for i in range(n - 2, -1, -1):
            if nums[i] <= nums[i + 1]:
                non_decreasing[i] = non_decreasing[i + 1] + 1

        result = []
        for i in range(k, n - k):
            if non_increasing[i - 1] >= k and non_decreasing[i + 1] >= k:
                result.append(i)

        return result
```
