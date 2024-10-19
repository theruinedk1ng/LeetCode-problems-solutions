419. Battleships in a Board
https://leetcode.com/problems/battleships-in-a-board/description/


PYTHON SOLUTION

```
class Solution:
    def countBattleships(self, board: List[List[str]]) -> int:
        if not board or not board[0]:
            return 0
        
        rows, cols = len(board), len(board[0])
        count = 0
        
        for i in range(rows):
            for j in range(cols):
                if board[i][j] == 'X':
                    if i > 0 and board[i-1][j] == 'X':
                        continue 
                    if j > 0 and board[i][j-1] == 'X':
                        continue  
                    count += 1
                    
        return count

```
