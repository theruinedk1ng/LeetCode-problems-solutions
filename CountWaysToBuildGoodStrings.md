2466. Count Ways To Build Good Strings
https://leetcode.com/problems/count-ways-to-build-good-strings/description/?envType=daily-question&envId=2024-12-30

PYTHON SOLUTION
```
class Solution:
    def countGoodStrings(self, low: int, high: int, zero: int, one: int) -> int:

        MOD = int(1e9 + 7)

        dp = {}

        def solve(length):

            if length > high:
                return 0

            if length in dp:
                return dp[length]

            is_good = 0

            if length >= low and length <= high:
                is_good = 1

            p1 = solve(length + zero)
            p2 = solve(length + one)

            dp[length] = (p1 + p2 + is_good) % MOD

            return dp[length]
        
        return solve(0)
```
