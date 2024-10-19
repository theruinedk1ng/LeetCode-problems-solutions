1545. Find Kth Bit in Nth Binary String
https://leetcode.com/problems/find-kth-bit-in-nth-binary-string/description/?envType=daily-question&envId=2024-10-19


PYTHON SOLUTION

```
class Solution:
    def findKthBit(self, n: int, k: int) -> str:
        
        rez = '0'

        def invert(s):

            return ''.join('1' if c == '0' else '0' for c in s)

        def func(x):

            return x + '1' + invert(x)[::-1]

        for i in range(n - 1):

            rez = func(rez)
        
        
        return rez[k - 1]
```
