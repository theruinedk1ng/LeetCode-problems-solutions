63. Unique Paths II
https://leetcode.com/problems/unique-paths-ii/description/



PYTHON SOLUTION USING DFS AND MEMOIZATION:

class Solution:
    def uniquePathsWithObstacles(self, obstacleGrid: List[List[int]]) -> int:

        m = len(obstacleGrid)
        n = len(obstacleGrid[0])

        memo = {}

        def dfs(x, y):

            if x >= m or y >= n or obstacleGrid[x][y] == 1:
                return 0
            
            if x == m - 1 and y == n - 1:
                return 1
            
            obstacleGrid[x][y] = 1

            if(x, y) in memo:
                return memo[(x,y)]

            r = dfs(x+1, y)
            l = dfs(x, y+1)

            obstacleGrid[x][y] = 0 
            memo[(x, y)] = r + l
            return memo[(x, y)]

        return dfs(0, 0)
