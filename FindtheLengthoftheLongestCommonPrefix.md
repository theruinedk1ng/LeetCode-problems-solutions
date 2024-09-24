3043. Find the Length of the Longest Common Prefix
https://leetcode.com/problems/find-the-length-of-the-longest-common-prefix/description/?envType=daily-question&envId=2024-09-24

PYTHON SOLUTION #1:
```
class Solution:
    def longestCommonPrefix(self, arr1: List[int], arr2: List[int]) -> int:
        prefixes = set()
        for elem in arr2:
            while elem > 0:
                prefixes.add(elem)
                elem //= 10
        
        result = 0
        for elem in arr1:
            while elem > result:
                if elem in prefixes:
                    result = max(result, elem)
                    break
                else:
                    elem //= 10
        
        if result == 0:
            return 0
        return len(str(result))
```

PYTHON SOLUTION #2:

```
class Solution:
    def longestCommonPrefix(self, arr1: List[int], arr2: List[int]) -> int:
        
        store = set()
        set1 = set(arr1)
        set2 = set(arr2)

        for i in set2:
            current = ''
            s = str(i)
            for j in s:
                current += j
                if int(current) not in store:
                    store.add(int(current))
        
        cnt = 0 

        for i in set1:
            current = ''
            s = str(i)
            for j in s:
                current += j
                if int(current) in store:
                    cnt = max(cnt, len(current))
        
        return cnt
