921. Minimum Add to Make Parentheses Valid
https://leetcode.com/problems/minimum-add-to-make-parentheses-valid/



PYTHON SOLUTION

```
class Solution:
    def minAddToMakeValid(self, s: str) -> int:

        stack = ['']
        rez = 0

        for i in s: 

            if stack and stack[-1] == '(' and i == ')':
                stack.pop()
            else:
                stack.append(i)

        aux = ''.join(stack)
    
        if aux == '':
            return 0

        return len(aux)


```
