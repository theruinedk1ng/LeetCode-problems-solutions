1331. Rank Transform of an Array
https://leetcode.com/problems/rank-transform-of-an-array/description/?envType=daily-question&envId=2024-10-02

PYTHON SOLUTION:

```
class Solution:
    def arrayRankTransform(self, arr: List[int]) -> List[int]:
      
        sorted_unique = sorted(set(arr))
        
        rank_dict = {}
        for rank, num in enumerate(sorted_unique):
            rank_dict[num] = rank + 1
        
        result = []
        for num in arr:
            result.append(rank_dict[num])
        
        return result
```
