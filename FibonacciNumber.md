509. Fibonacci Number
https://leetcode.com/problems/fibonacci-number/description/


PYTHON SOLUTION #1
```
class Solution:
    def fib(self, n: int) -> int:

        f = []
        f.append(0)
        f.append(1)

        if n == 1:
            return 1
        if n == 0:
            return 0
        
        for i in range(2, n+1):

            f.append(f[i-1] + f[i-2])

        return f[n]
        
```

PYTHON SOLUTION #2

```
class Solution:
    def fib(self, n: int) -> int:

        def recursive(n):

            if n<=1:
                return n

            return recursive(n-1)+recursive(n-2)
            
        k=recursive(n)

        return k
```
