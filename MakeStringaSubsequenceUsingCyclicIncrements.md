2825. Make String a Subsequence Using Cyclic Increments
https://leetcode.com/problems/make-string-a-subsequence-using-cyclic-increments/description/?envType=daily-question&envId=2024-12-04

PYTHON SOLUTION

```
class Solution:
    def canMakeSubsequence(self, str1: str, str2: str) -> bool:

        n = len(str1)
        m = len(str2)
        
        if n < m:
            return False
        
        i, j = 0, 0  
        
        while i < n and j < m:
 
            if str1[i] == str2[j] or chr(((ord(str1[i]) - ord('a') + 1) % 26) + ord('a')) == str2[j]:
                j += 1 
            i += 1 
 
        return j == m

```
