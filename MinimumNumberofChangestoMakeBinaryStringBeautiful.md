2914. Minimum Number of Changes to Make Binary String Beautiful
https://leetcode.com/problems/minimum-number-of-changes-to-make-binary-string-beautiful/description/?envType=daily-question&envId=2024-11-05


PYTHON SOLUTION
```
class Solution:
    def minChanges(self, s: str) -> int:
        
        rez = 0

        for i in range(0, len(s) - 1, 2):
            
            if s[i] != s[i + 1]:
                rez += 1
        
        return rez
```
