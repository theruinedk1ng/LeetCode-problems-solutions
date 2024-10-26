1137. N-th Tribonacci Number
https://leetcode.com/problems/n-th-tribonacci-number/description/?envType=study-plan-v2&envId=dynamic-programming


PYTHON SOLUTION #1

```
class Solution:
    def tribonacci(self, n: int) -> int:

        l = [0, 1, 1]

        for i in range(2, n + 1):
            l.append(l[i] + l[i - 1] + l[i - 2])
        
        return l[n]

```



PYTHON SOLUTION #2

```
class Solution:
    def tribonacci(self, n: int) -> int:
        var0, var1, var2 = 0, 1, 1
        if n == 0:
            return var0
        if n < 3:
            return var1
        for i in range(3, n+1):
            sum = var0 + var1 + var2
            var0, var1, var2 = var1, var2, sum
        return sum
```
