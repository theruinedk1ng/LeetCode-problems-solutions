67. Add Binary
https://leetcode.com/problems/add-binary/

PYTHON SOLUTION 
```
class Solution:
    def addBinary(self, a: str, b: str) -> str:


        a = int(a, 2)
        b = int(b, 2)

        rez = bin(a+b)[2:]
        
        return rez

```
