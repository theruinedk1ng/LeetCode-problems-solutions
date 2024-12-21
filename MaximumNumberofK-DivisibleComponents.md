2872. Maximum Number of K-Divisible Components
https://leetcode.com/problems/maximum-number-of-k-divisible-components/description/

PYTHON SOLUTION
```
class Solution:
    def maxKDivisibleComponents(self, n: int, edges: List[List[int]], values: List[int], k: int) -> int:
   
        adj = {i: set() for i in range(n)}
        for a, b in edges:
            adj[a].add(b)
            adj[b].add(a)
        
        
        visited_edges = set()
        result = 0
        
        def func(node: int, parent: int) -> int:
           
            subtree_sum = values[node]
            
            for neighbor in adj[node]:
      
                if (node, neighbor) not in visited_edges and (neighbor, node) not in visited_edges:
                    visited_edges.add((node, neighbor))
                    visited_edges.add((neighbor, node))
                    subtree_sum += func(neighbor, node)
            
            if subtree_sum % k == 0:
                nonlocal result
                result += 1
                return 0
            
            return subtree_sum
        
        func(0, -1)
        return result

```
