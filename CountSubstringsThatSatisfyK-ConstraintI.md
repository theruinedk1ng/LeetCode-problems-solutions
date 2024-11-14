3258. Count Substrings That Satisfy K-Constraint I
https://leetcode.com/problems/count-substrings-that-satisfy-k-constraint-i/description/

PYTHON SOLUTION
```
class Solution:
    def countKConstraintSubstrings(self, s: str, k: int) -> int:
        
        res = 0
        l = Counter(list(s))
        if l['0'] <= k or l['1'] <= k:
            res += 1

        def slide(n, cnt):

            st = 0
            end = n
            while end <= len(s):

                print(s[st:end])
                l = Counter(list(s[st:end]))
                
                if l['0'] <= k or l['1'] <= k:
                    cnt += 1

                st += 1
                end += 1

            return cnt
        

        for i in range(1, len(s)):
            res += slide(i, 0)

        return res



```
