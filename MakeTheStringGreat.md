1544. Make The String Great
https://leetcode.com/problems/make-the-string-great/description/

PYTHON SOLUTION
```
class Solution:
    def makeGood(self, s: str) -> str:

        stack = []

        for c in s:
            if stack and (stack[-1] == c.upper() or stack[-1].upper() == c) and stack[-1] != c:
                stack.pop()
            else:
                stack.append(c)

        return "".join(stack)
```
