316. Remove Duplicate Letters
https://leetcode.com/problems/remove-duplicate-letters/description/

PYTHON SOLUTION

```
class Solution:
    def removeDuplicateLetters(self, s: str) -> str:
        
        x = Counter(s)
        stack = []
        seen = set()


        for i in s:

            x[i] -= 1
        
            if i in seen:
                continue

            while stack and stack[-1] > i and x[stack[-1]] > 0:
                seen.remove(stack.pop())
            
            seen.add(i)
            stack.append(i)

        
        return ''.join(stack)

```
