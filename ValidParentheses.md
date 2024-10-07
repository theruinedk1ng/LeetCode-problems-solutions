20. Valid Parentheses
https://leetcode.com/problems/valid-parentheses/description/?envType=problem-list-v2&envId=stack&difficulty=EASY


PYTHON SOLUTION

```
class Solution:
    def isValid(self, s: str) -> bool:
        
        stack = ['']


        for x in s:

            if stack and stack[-1] == '(' and x == ')':
                stack.pop()
            elif stack and stack[-1] == '[' and x == ']':
                stack.pop()
            elif stack and stack[-1] == '{' and x == '}':
                stack.pop()
            else:
                stack.append(x)
        

        if len(stack) != 1:
            return False
        return True
```
