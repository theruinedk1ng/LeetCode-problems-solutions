2966. Divide Array Into Arrays With Max Difference
https://leetcode.com/problems/divide-array-into-arrays-with-max-difference/description/

PYTHON SOLUTION
```
class Solution:
    def divideArray(self, nums: List[int], k: int) -> List[List[int]]:

        n = len(nums)
        nums.sort() 

        result = []
        aux = []
        counter = 0

        for i in range(n):
            if counter == 3:
                if aux[2] - aux[0] > k:
                    return []
                
                counter = 0
                result.append(aux)
                aux = []
            counter += 1
            aux.append(nums[i])
        
        if counter == 3:
            if aux[2] - aux[0] > k:
                return []
            result.append(aux)
        
        return result
```
