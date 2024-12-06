2337. Move Pieces to Obtain a String
https://leetcode.com/problems/move-pieces-to-obtain-a-string/description/

PYTHON SOLUTION

```
class Solution:
    def canChange(self, start: str, target: str) -> bool:

        if start.replace('_', '') != target.replace('_', ''):
            return False
        
        n = len(start)

        start_positions = [(char, i) for i, char in enumerate(start) if char != '_']

        target_positions = [(char, i) for i, char in enumerate(target) if char != '_']
        
        for (s_char, s_idx), (t_char, t_idx) in zip(start_positions, target_positions):
   
            if s_char == 'L' and s_idx < t_idx:
                return False

            if s_char == 'R' and s_idx > t_idx:
                return False
        
        return True
```
