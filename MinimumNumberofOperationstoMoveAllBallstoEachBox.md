1769. Minimum Number of Operations to Move All Balls to Each Box
https://leetcode.com/problems/minimum-number-of-operations-to-move-all-balls-to-each-box/description/?envType=daily-question&envId=2025-01-06

PYHTON SOLUTION #1
```
class Solution:
    def minOperations(self, boxes: str) -> List[int]:
        
        n = len(boxes)
        distances = [0] * n

        prefixCount = 0
        prefixSum = 0

        for i in range(n):
            distances[i] = prefixCount * i - prefixSum
            if boxes[i] == '1':
                prefixCount += 1
                prefixSum += i

        suffixCount = 0
        suffixSum = 0

        for i in range(n - 1, -1, -1):
            distances[i] += suffixSum - suffixCount * i
            if boxes[i] == '1':
                suffixCount += 1
                suffixSum += i

        return distances
```

PYTHON SOLUTION #2
```
class Solution:
    def minOperations(self, boxes: str) -> List[int]:

        n = len(boxes)
        result = [0] * n

        for i in range(n):
            for j in range(n):
                if boxes[j] == '1':
                    result[i] += abs(j - i)
```
