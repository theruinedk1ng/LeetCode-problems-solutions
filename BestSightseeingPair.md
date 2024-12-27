1014. Best Sightseeing Pair
https://leetcode.com/problems/best-sightseeing-pair/?envType=daily-question&envId=2024-12-27

PYTHON SOLUTION

```
class Solution:
    def maxScoreSightseeingPair(self, values: List[int]) -> int:
        
        n = len(values)

        if n == 2:
            return values[0] + values[1] - 1
        
        index = 0
        result = -float('inf')

        for i in range(1, n - 1):

            if i != index and values[index] + values[i] - i + index > result:
                result = values[index] + values[i] - i + index
            if i != index and values[i] + i >= values[index] + index:
                index = i
        
        if values[index] + values[n - 1] + index - n + 1 > result:
            result = values[index] + values[n - 1] + index - n + 1
            
        
        return result
```
