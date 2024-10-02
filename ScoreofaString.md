3110. Score of a String
https://leetcode.com/problems/score-of-a-string/description/

PYTHON SOLUTION:
```
class Solution:
    def scoreOfString(self, s: str) -> int:
        
        score = 0

        s = list(s)

        st = 0
        end = len(s)

        while st < end - 1:

            score += abs(ord(s[st]) - ord(s[st+1]))
            st += 1

        return score
```
