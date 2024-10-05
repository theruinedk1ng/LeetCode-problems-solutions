1108. Defanging an IP Address
https://leetcode.com/problems/defanging-an-ip-address/

PYTHON SOLUTION

```
class Solution:
    def defangIPaddr(self, address: str) -> str:

        rez = ''
        address = list(address)

        for i in address:

            if i != '.':
                rez += str(i)
            else:
                rez += '[.]'
                
        return rez        

        
```
