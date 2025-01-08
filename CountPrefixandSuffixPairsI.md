3042. Count Prefix and Suffix Pairs I
https://leetcode.com/problems/count-prefix-and-suffix-pairs-i/description/?source=submission-noac

PYTHON SOLUTION
```
class Solution:
    def countPrefixSuffixPairs(self, words: List[str]) -> int:
        
        pairs = 0
        n = len(words)

        def isPrefixAndSufix(str1, str2, x):
            return str1 == str2[ : x] and str1 == str2[-x : ]

        for i in range(n):
            x = len(words[i])
            for j in range(i +1, n):
                if len(words[j]) >= x:
                    pairs += isPrefixAndSufix(words[i], words[j], x)

        return pairs 



```
