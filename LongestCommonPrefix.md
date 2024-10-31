14. Longest Common Prefix
https://leetcode.com/problems/longest-common-prefix/description/

PYTHON SOLUTION

```
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
    
        res = ''
        n = len(strs)
        i = 0
        aux = strs[0]

        if n == 1:
            return strs[0]
        elif '' in strs:
            return ''
        elif n > 1 and len(set(strs)) == 1:
            return strs[0]
        
        m = float('inf')
        for word in strs:
            if len(word) < m:
                m = len(word)
        
        def func(x, s, p, m):
            
            for words in s:
                if words[p] != x:
                    return False
            return True
        
        while i < m and func(aux[i], strs, i, m):
            res += aux[i]
            i += 1


        return res
```
