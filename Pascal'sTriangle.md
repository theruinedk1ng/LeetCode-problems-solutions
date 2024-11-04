118. Pascal's Triangle
https://leetcode.com/problems/pascals-triangle/description/

PYTHON SOLUTION  
```
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        
        rez = [[1], [1, 1]]

        if numRows == 1:
            return [[1]]
        elif numRows == 2:
            return rez
        
        aux = []

        for i in range(3, numRows + 1):
            for j in range(i):
                if j == 0 or j == i - 1:
                    aux.append(1)
                else:
                    aux.append(rez[i - 2][j - 1] + rez[i - 2][j])

            rez.append(aux)
            aux = []
        return rez

```
