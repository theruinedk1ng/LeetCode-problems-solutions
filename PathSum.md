112. Path Sum
https://leetcode.com/problems/path-sum/description/

PYTHON SOLUTION
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
from collections import deque 
class Solution:
    def hasPathSum(self, root: Optional[TreeNode], targetSum: int) -> bool:
        
        if root is None:
            return False

        q = deque()
        q.append((root, 0))

        while q:
            current, s = q.popleft() 
            if current.left:
                q.append((current.left, s + current.val))
            if current.right:
                q.append((current.right, s + current.val))
            if s + current.val == targetSum and not current.left and not current.right:
                return True

        return False
        

```
