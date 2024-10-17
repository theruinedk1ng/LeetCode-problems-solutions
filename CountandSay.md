38. Count and Say
https://leetcode.com/problems/count-and-say/description/

PYTHON SOLUTION

```
class Solution:
    def countAndSay(self, n: int) -> str:


        def func(x):

            x = list(str(x))

            aux = ''
            cnt = 1
            prev = x[0]

            for i in range(1, len(x)):

                if x[i] == prev:
                    
                    cnt += 1
                else:

                    aux += str(cnt) + prev
                    prev = x[i]
                    cnt = 1
            aux += str(cnt) + prev
            return aux
        
        t = '1'

        for i in range(n-1):

            t = func(t)
        
        return t
```
