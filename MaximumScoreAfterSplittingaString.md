1422. Maximum Score After Splitting a String
https://leetcode.com/problems/maximum-score-after-splitting-a-string/description/

PYTHON SOLUTION
```
class Solution:
    def maxScore(self, s: str) -> int:
        
        x = list(s)
        n = len(x)

        prefix_sum = [0] * n
        prefix_sum[0] = int(x[0])

        for i in range(1, n):
            prefix_sum[i] = prefix_sum[i - 1] + int(x[i])
        
        if prefix_sum[n - 1] == 0 or prefix_sum[n - 1] == n:
            return n - 1

        result = max(prefix_sum) - 1

        for i in range(n - 1):

            result = max(result, prefix_sum[n - 1] - prefix_sum[i] + i + 1 - prefix_sum[i])

        return result

```
