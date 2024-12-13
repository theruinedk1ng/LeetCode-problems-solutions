2593. Find Score of an Array After Marking All Elements
https://leetcode.com/problems/find-score-of-an-array-after-marking-all-elements/description/?envType=daily-question&envId=2024-12-13

Python Solution
```
class Solution:
    def findScore(self, nums: List[int]) -> int:
        
        score = 0
        n = len(nums)
        mark = set()

        arr = []
        for i, num in enumerate(nums):
            heapq.heappush(arr, (num, i))

        while arr:
            x = heapq.heappop(arr)
            if x[1] not in mark:
                mark.add(x[1])
                score += x[0]
                if x[1] - 1 >= 0:
                    mark.add(x[1] - 1)
                if x[1] + 1 < n:
                    mark.add(x[1] + 1)

        return score

```
