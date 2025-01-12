2116. Check if a Parentheses String Can Be Valid
https://leetcode.com/problems/check-if-a-parentheses-string-can-be-valid/description/?envType=daily-question&envId=2025-01-12

PYTHON SOLUTION
```
class Solution:
    def canBeValid(self, s: str, locked: str) -> bool:
        
        n = len(s)

        if n % 2 == 1:
            return False

        open_count = 0 

        for i in range(n):

            if locked[i] == '0' or s[i] == '(':
                open_count += 1  
            else:
                open_count -= 1  
            if open_count < 0:  
                return False

        close_count = 0 

        for i in range(n - 1, -1, -1):
            
            if locked[i] == '0' or s[i] == ')':
                close_count += 1  
            else:
                close_count -= 1  
            if close_count < 0: 
                return False

        return True

```
