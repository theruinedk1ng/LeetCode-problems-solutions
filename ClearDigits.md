3174. Clear Digits
https://leetcode.com/problems/clear-digits/description/?envType=problem-list-v2&envId=stack&difficulty=EASY


PYTHON SOLUTION #1

```
class Solution:
    def clearDigits(self, s: str) -> str:
        items = []

        for item in s:
            if item.isdigit():
                if items:
                    items.pop()
            else:
                items.append(item)
        
        return "".join(items)
```


PYTHON SOLUTION #2

```
class Solution:
    def clearDigits(self, s: str) -> str:
        
        rez = ''
        stack = ['']

        for i in range(len(s)):

            if stack and stack[-1].isalpha() and s[i].isdigit():
                stack.pop()
            else:
                stack.append(s[i])
        
        for i in stack:
            rez += i
        
        return rez
```
