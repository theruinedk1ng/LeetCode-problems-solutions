1791. Find Center of Star Graph
https://leetcode.com/problems/find-center-of-star-graph/description/


PYTHON SOLUTION #1

```
class Solution:
    def findCenter(self, edges: List[List[int]]) -> int:

        n = len(edges)
        freq = [0] * (n + 2)
        for a,b in edges:
            freq[a] += 1
            freq[b] += 1
        for i in range(1, n + 2):
            if freq[i] == n:
                return i

        return 0
```

PYTHON SOLUTION #2

```
class Solution:
    def findCenter(self, edges: List[List[int]]) -> int:
        
        arr = []

        for edge in edges:
            for e in edge:
                arr.append(e)
        
        f = Counter(arr)
        arr = set(arr)

        for i in arr:

            if f[i] == len(arr) - 1:
                return i
        
```
