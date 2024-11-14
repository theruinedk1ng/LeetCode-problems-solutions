2070. Most Beautiful Item for Each Query
https://leetcode.com/problems/most-beautiful-item-for-each-query/description/?envType=daily-question&envId=2024-11-12

PYTHON SOLUTION

```
class Solution:
    def maximumBeauty(self, items: List[List[int]], queries: List[int]) -> List[int]:
        
        items.sort()
        
        max_beauties = []
        current_max_beauty = 0

        for price, beauty in items:
            current_max_beauty = max(current_max_beauty, beauty)
            max_beauties.append((price, current_max_beauty))
        
        
        sorted_queries = sorted((query, i) for i, query in enumerate(queries))
        result = [0] * len(queries)
        
        for query, idx in sorted_queries:
            pos = bisect_right(max_beauties, (query, float('inf'))) - 1
            if pos >= 0:
                result[idx] = max_beauties[pos][1]
        
        return result
```
