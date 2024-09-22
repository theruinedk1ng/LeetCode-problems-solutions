1. Two Sum
https://leetcode.com/problems/two-sum/description/

PYTHON SOLUTION #1

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        
        i = 0 
        for i in range(len(nums)):
            for j in range(i+1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]


        

PYTHON SOLUTION #2

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_indices = {}

        for i, num in enumerate(nums):
            complement = target - num
            if complement in num_indices:

                return [num_indices[complement], i]
            
            num_indices[num] = i

        return []
