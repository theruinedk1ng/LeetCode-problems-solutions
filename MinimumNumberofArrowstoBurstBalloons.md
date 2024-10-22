452. Minimum Number of Arrows to Burst Balloons
https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/description/


PYTHON SOLUTION #1  

```
class Solution:
    def findMinArrowShots(self, points: List[List[int]]) -> int:
        points.sort(key=lambda x:x[1])

        count = 0
        lastarrow = None
        for point in points:
            if lastarrow is None or lastarrow < point[0]:
                count += 1
                lastarrow = point[1]
        return count
```

PYTHON SOLUTION #2

```
class Solution:
    def findMinArrowShots(self, points: List[List[int]]) -> int:

        arrows = 1
        points.sort()
        aux = points[0]
        print(points)

        if len(points) == 2 and points[0] == points[1]:
            return 1

        for i in range(1, len(points)):
            
            if points[i][0] > aux[1]:
                arrows += 1
                aux = points[i]
            else:
                aux[1] = min(aux[1], points[i][1])
        

        return arrows
```
