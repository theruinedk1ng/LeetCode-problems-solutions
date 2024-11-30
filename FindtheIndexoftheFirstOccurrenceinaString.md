28. Find the Index of the First Occurrence in a String
https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/description/

PYTHON SOLUTION #1

```
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        
        if not needle:
            return 0
        
        
        if len(needle) > len(haystack):
            return -1
        
       
        for i in range(len(haystack) - len(needle) + 1):
            
            if haystack[i:i+len(needle)] == needle:
                return i
        
       
        return -1
 
```

PYTHON SOLUTION #2

```
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:

        if haystack == needle:
            return 0
        
        if len(needle) == 1:
            for i in range(len(haystack)):
                if haystack[i] == needle:
                    return i

        for i in range(len(haystack) - 1):
            sub = ''
            sub += haystack[i]
            for j in range(i + 1, len(haystack)):
                sub += haystack[j]
                if sub == needle:
                    return i
        
        return -1
```
