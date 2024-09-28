13. Roman to Integer
https://leetcode.com/problems/roman-to-integer/description/

PYTHON SOLUTION:
```
class Solution:
    def romanToInt(self, s: str) -> int:
        
        aux = 0
        s += 'I'

        def ident(x: str) -> int:
            if x == 'I':
                return 1
            if x == 'V':
                return 5
            if x == 'X':
                return 10
            if x == 'L':
                return 50
            if x == 'C':
                return 100
            if x == 'D':
                return 500
            if x == 'M':
                return 1000
            
        
        i = 0
        
        while i < len(s):
            
            if i+1 < len(s) and ident(s[i]) >= ident(s[i+1]):
                aux += ident(s[i])
            elif i+1 < len(s) and ident(s[i]) < ident(s[i+1]):
                aux += (ident(s[i+1]) - ident(s[i]))
                i += 1
            i += 1

        return aux
```

            
            
            
