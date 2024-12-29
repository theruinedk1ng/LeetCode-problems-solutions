202. Happy Number
https://leetcode.com/problems/happy-number/description/

PYTHON SOLUTION
```
class Solution:
    def isHappy(self, n: int) -> bool:
        
        d = set()

        if n == 1:
            return True
        
        while n != 1:

            digits = list(str(n))
            s = 0

            for digit in digits:
                s += int(digit) ** 2
            
            if s not in d:
                d.add(s)
            else:
                return False
            
            n = s
        
        return True
```
