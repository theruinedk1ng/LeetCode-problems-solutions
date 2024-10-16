2938. Separate Black and White Balls
https://leetcode.com/problems/separate-black-and-white-balls/?envType=daily-question&envId=2024-10-15


PYTHON SOLUTION 

```
class Solution:
    def minimumSteps(self, s: str) -> int:
        
        s = list(map(int, s))
        steps = 0
        cnt = 0

        for i in range(len(s)):

            if s[i] == 0:
                steps += i - cnt
                cnt += 1




        return steps

```
