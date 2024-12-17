2182. Construct String With Repeat Limit
https://leetcode.com/problems/construct-string-with-repeat-limit/description/

PYTHON SOLUTION
```
import heapq
from collections import Counter

class Solution:
    def repeatLimitedString(self, s: str, repeatLimit: int) -> str:
        
        result = [] 
        freq = Counter(s)  
        max_heap = [(-ord(char), char) for char in freq] 
        heapq.heapify(max_heap)

        prev_count = 0  
        prev_char = None 

        while max_heap:
            v, char = heapq.heappop(max_heap)  
            
            if char == prev_char and prev_count >= repeatLimit:  

                if not max_heap:  
                    break
                
                v_next, next_char = heapq.heappop(max_heap)
                result.append(next_char)
                freq[next_char] -= 1

                if freq[next_char] > 0:
                    heapq.heappush(max_heap, (v_next, next_char))
                
                heapq.heappush(max_heap, (v, char))
                
                prev_char, prev_count = next_char, 1
            else:

                add_count = min(freq[char], repeatLimit)
                result.append(char * add_count)
                freq[char] -= add_count

                prev_char, prev_count = char, add_count

                if freq[char] > 0:
                    heapq.heappush(max_heap, (v, char))

        return ''.join(result)

```
