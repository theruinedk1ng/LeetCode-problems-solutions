1346. Check If N and Its Double Exist
https://leetcode.com/problems/check-if-n-and-its-double-exist/description/?envType=daily-question&envId=2024-12-01

PYTHON SOLUTION 1

```
class Solution:
    def checkIfExist(self, arr: List[int]) -> bool:
        
        d = {}
        counter = 0

        for x in arr:
            if x == 0:
                counter += 1
            d[x] = True
        
        if counter > 1:
            return True

        for x in arr:
            if 2 * x in d and x != 0:
                return True
        
        return False
```

PYTHON SOLUTION 2

```
class Solution:
    def checkIfExist(self, arr: List[int]) -> bool:
        
        i = 0
        j = len(arr) - 1

        while i != (len(arr) - 1):

            if i < j:
                if arr[i] == 2 * arr[j] or arr[i] * 2 == arr[j]:
                    return True
                else:
                    j -= 1
            else:
                i += 1
                j = len(arr) - 1
            
        return False
```

PYTHON SOLUTION 3

```
class Solution:
    def checkIfExist(self, nums: List[int]) -> bool:
        
        mp={}

        for i in range(len(nums)):
            if nums[i]*2 in mp or nums[i]/2 in mp:
                return True
                

            else:
                mp[nums[i]]=1+mp.get(nums[i],0)
        return False
                
```
