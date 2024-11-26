1971. Find if Path Exists in Graph
https://leetcode.com/problems/find-if-path-exists-in-graph/description/


PYTHON SOLUTION
```
class Solution:
    def validPath(self, n: int, edges: List[List[int]], source: int, destination: int) -> bool:

        if n == 1:
            return True

        def dfs(graph, x, visited = None):

            if visited is None:
                visited = set()

            visited.add(x)

            for nxt in graph[x] - visited:
                dfs(graph, nxt, visited)
            
            return visited
        
        g = {}

        for a, b in edges:
            if a not in g:
                g[a] = set()
            if b not in g:
                g[b] = set()
            g[a].add(b)
            g[b].add(a)
        

        if destination in dfs(g, source):
            return True
        return False
```
