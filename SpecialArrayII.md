3152. Special Array II
https://leetcode.com/problems/special-array-ii/description/?envType=daily-question&envId=2024-12-09

PYTHON SOLUTION

```
class Solution:
    def isArraySpecial(self, nums: List[int], queries: List[List[int]]) -> List[bool]:
       
        n = len(nums)

        parity = [1] * (n - 1)

        for i in range(n - 1):
            if nums[i] % 2 == nums[i + 1] % 2: 
                parity[i] = 0
        
        prefix_sum = [0] * n
        
        for i in range(1, n):
            prefix_sum[i] = prefix_sum[i - 1] + (1 - parity[i - 1])  
        
        result = []

        for left, right in queries:
            if prefix_sum[right] - prefix_sum[left] > 0: 
                result.append(False)
            else:
                result.append(True)
        
        return result

```
