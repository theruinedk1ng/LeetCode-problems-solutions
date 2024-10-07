2696. Minimum String Length After Removing Substrings
https://leetcode.com/problems/minimum-string-length-after-removing-substrings/description/?envType=daily-question&envId=2024-10-07


PYTHON SOLUTION

```
class Solution:
    def minLength(self, s: str) -> int:
        
        stack = []

        for x in s:

            if stack and stack[-1] == 'A' and x == 'B':

                stack.pop()

            elif stack and stack[-1] == 'C' and x == 'D':
                
                stack.pop()

            else:

                stack.append(x)
        
        return len(stack)
```
