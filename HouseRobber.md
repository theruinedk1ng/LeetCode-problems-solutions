198. House Robber
https://leetcode.com/problems/house-robber/description/?envType=study-plan-v2&envId=dynamic-programming


PYTHON SOLUTION
```
class Solution:
    def rob(self, nums: List[int]) -> int:
        
        n = len(nums)

        dp = [0] * n

        if n == 1:
            return nums[0]
        elif n == 2:
            return max(nums[0], nums[1])
        
        dp[0] = nums[0]
        dp[1] = max(dp[0], nums[1])

        for i in range(2, n):

            dp[i] = max(dp[i - 2] + nums[i], dp[i - 1])

        return dp[n - 1]
```
