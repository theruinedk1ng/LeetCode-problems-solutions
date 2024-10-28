746. Min Cost Climbing Stairs
https://leetcode.com/problems/min-cost-climbing-stairs/description/?envType=study-plan-v2&envId=dynamic-programming

PYTHON SOLUTION 
```
class Solution:
    def minCostClimbingStairs(self, cost: List[int]) -> int:
        
        n = len(cost)
        dp = [0] * n

        if n == 1:
            return cost[0]
        elif n == 2:
            return min(cost[0], cost[1])
        
        dp[0] = cost[0]
        dp[1] = cost[1]

        for i in range(2, n):
            dp[i] = min(cost[i] + dp[i - 1], cost[i] + dp[i - 2])
        
        return min(dp[n - 2], dp[n - 1])
```
