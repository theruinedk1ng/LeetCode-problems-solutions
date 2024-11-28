2290. Minimum Obstacle Removal to Reach Corner
https://leetcode.com/problems/minimum-obstacle-removal-to-reach-corner/description/?envType=daily-question&envId=2024-11-28

PYTHON SOLUTION  
```
from collections import deque

class Solution:
    def minimumObstacles(self, grid: List[List[int]]) -> int:
    
        def is_valid(i, j):
            if i < 0 or i >= m:
                return False
            if j < 0 or j >= n:
                return False
            return True

        m = len(grid)
        n = len(grid[0])

        adj = [(-1, 0), (0, 1), (1, 0), (0, -1)]

        def BFS(si, sj, counter, costs):

            q = deque()

            q.append((si, sj))

            costs[si][sj] = 0

            while q:
                
                e = q.popleft()
                i = e[0]
                j = e[1]

                for ip, jp in adj:

                    if is_valid(i + ip, j + jp):
                        
                        if grid[i + ip][j + jp] == 0:
                            if costs[i][j] < costs[i + ip][j + jp]:
                                costs[i + ip][j + jp] = costs[i][j]

                                q.appendleft((i + ip, j + jp))

                        elif grid[i + ip][j + jp] == 1:
                            if costs[i][j]  + 1 < costs[i + ip][j + jp]:
                                costs[i + ip][j + jp] = costs[i][j] + 1

                                q.append((i + ip, j + jp))

        costs = []

        for i in range(m):
            costs.append([float("inf")] * n)

        BFS(0, 0, 0, costs)

        return costs[m - 1][n - 1]

```
