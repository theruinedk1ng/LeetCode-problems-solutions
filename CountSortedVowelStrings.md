1641. Count Sorted Vowel Strings
https://leetcode.com/problems/count-sorted-vowel-strings/description/

PYTHON SOLUTION
```
class Solution:
    def countVowelStrings(self, n: int) -> int:

        memo = {5: 1, 4: 1, 3: 1, 2: 1, 1: 1}

        for i in range(2, n + 1):
            for key in range(5, 0, -1):
                memo[key] += memo.get(key + 1, 0)
        
        return sum(memo.values())

```
