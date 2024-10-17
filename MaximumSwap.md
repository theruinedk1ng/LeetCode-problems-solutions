670. Maximum Swap
https://leetcode.com/problems/maximum-swap/description/?envType=daily-question&envId=2024-10-17

PYTHON SOLUTION

```
class Solution:
    def maximumSwap(self, num: int) -> int:

        mx = num
        num = list(str(num))
        for i in range(len(num)-1):
            for j in range(i + 1, len(num)):
                num[i], num[j] = num[j], num[i]
                aux = int(''.join(num))
                if aux > mx:
                    mx = aux
                num[j], num[i] = num[i], num[j]
        return mx
```
