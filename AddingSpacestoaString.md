2109. Adding Spaces to a String
https://leetcode.com/problems/adding-spaces-to-a-string/description/?envType=daily-question&envId=2024-12-03

PYTHON SOLUTION

```
class Solution:
    def addSpaces(self, s: str, spaces: List[int]) -> str:

        result = []  
        space_count = 0  
        n = len(spaces)  

        for i, j in enumerate(s):
       
            if space_count < n and i == spaces[space_count]:
                result.append(' ')  
                space_count += 1  
            
            result.append(j)  
        
        return ''.join(result)


```
