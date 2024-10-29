213. House Robber II
https://leetcode.com/problems/house-robber-ii/description/

PYTHON SOLUTION

```
class Solution:
    def rob(self, nums: List[int]) -> int:

        n = len(nums)

        if n == 1:
            return nums[0]
        elif n == 2:
            return max(nums)
        elif n == 3:
            return max(nums)
        
        def func(nums):

            dp = [0] * len(nums)
            dp[0] = nums[0]
            dp[1] = max(nums[0], nums[1])
            for i in range(2, len(nums)):
                dp[i] = max(dp[i - 1], nums[i] + dp[i - 2])
            
            return dp[-1]

        return max(func(nums[:-1]), func(nums[1:]))      
```
