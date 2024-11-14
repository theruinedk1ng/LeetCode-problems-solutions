219. Contains Duplicate II
https://leetcode.com/problems/contains-duplicate-ii/description/


```
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        
        l = Counter(nums)
        f = set(nums)
        d = []

        index = list(enumerate(nums))
        sorted_index= sorted(index, key=lambda x: x[1])
        sorted_nums = [x[1] for x in sorted_index]      
        original_indexes = [x[0] for x in sorted_index]
        
        st = 0 
        end = 1

        for i in f:
            
            if l[i] > 1:
                
                while end < len(nums):
                    if sorted_nums[st] == sorted_nums[end]:
                        if abs(original_indexes[st] - original_indexes[end]) <= k:
                            return True
                    st += 1
                    end += 1

            end = 1
            st = 0



        return False
```
