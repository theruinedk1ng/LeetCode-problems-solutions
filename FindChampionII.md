2924. Find Champion II
https://leetcode.com/problems/find-champion-ii/description/?envType=daily-question&envId=2024-11-26


PYTHON SOLUTION

```
class Solution:
    def findChampion(self, n: int, edges: List[List[int]]) -> int:

        degree = [True] * n

        for edge in edges:
            degree[edge[1]] = False
        
        counter = 0
        res = 0

        for i in range(n):
            if degree[i] == True:
                res = i
                counter += 1
        
        if counter > 1:
            return -1

        return res
        
```
