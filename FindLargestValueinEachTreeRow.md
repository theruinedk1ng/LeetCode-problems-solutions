515. Find Largest Value in Each Tree Row
https://leetcode.com/problems/find-largest-value-in-each-tree-row/submissions/1488273889/?envType=daily-question&envId=2024-12-25


PYTHON SOLUTION
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def largestValues(self, root: Optional[TreeNode]) -> List[int]:
        
        if root == None:
            return []

        queue = deque()
        queue.append((root, 0))
        d = {}
        result = []

        while queue:

            current, level = queue.popleft()

            if level not in d:
                d[level] = []    

            d[level].append(current.val)

            if current.left:
                queue.append((current.left, level + 1))
            if current.right:
                queue.append((current.right, level + 1))

        for value in d.values():
            result.append(max(value))
        
        return result
```
