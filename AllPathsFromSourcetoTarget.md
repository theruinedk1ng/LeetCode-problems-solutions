797. All Paths From Source to Target
https://leetcode.com/problems/all-paths-from-source-to-target/description/

PYTHON SOLUTION
```
class Solution:
    def allPathsSourceTarget(self, graph: List[List[int]]) -> List[List[int]]:
       
        ans = []
      
        def dfs(node, path):
        
            if node == len(graph) - 1:
                ans.append(path)

            for n in graph[node]:
                dfs(n, path + [n])
        
        dfs(0, [0])

        return ans

```
