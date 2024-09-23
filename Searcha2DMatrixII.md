240. Search a 2D Matrix II
https://leetcode.com/problems/search-a-2d-matrix-ii/description/

PYTHON SOLUTION:

```
class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        
        var = False

        for i in range(len(matrix)):
            for j in range(len(matrix[i])):
                if matrix[i][j] == target:
                    var = True
        return var

```
C++ SOLUTION:

```
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        
 
        for( int i =0 ; i < matrix.size() ; i ++ )
            for( int j = 0 ; j < matrix[i].size() ; j ++ )
                if( matrix[i][j] == target )
                    return true ;

        return false ;
    }
};

