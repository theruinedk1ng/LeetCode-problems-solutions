1963. Minimum Number of Swaps to Make the String Balanced
https://leetcode.com/problems/minimum-number-of-swaps-to-make-the-string-balanced/description/?envType=daily-question&envId=2024-10-08


PYTHON SOLUTION

```
class Solution:
    def minSwaps(self, s: str) -> int:

        var = 0
        swaps = 0

        for i in s:

            if i == '[':
                var -= 1
            else:
                var += 1
        
            if var > 0:

                swaps += 1
                var -= 2
        
        return swaps
        
```
