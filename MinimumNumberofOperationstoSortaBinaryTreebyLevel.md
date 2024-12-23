2471. Minimum Number of Operations to Sort a Binary Tree by Level
https://leetcode.com/problems/minimum-number-of-operations-to-sort-a-binary-tree-by-level/?envType=daily-question&envId=2024-12-23

PYTHON SOLUTION
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def minimumOperations(self, root: Optional[TreeNode]) -> int:
        
        queue = deque()
        queue.append((root, 0))
        d = {}
        result = 0

        while queue:

            current, level = queue.popleft()

            if level not in d:
                d[level] = []    

            d[level].append(current.val)

            if current.left:
                queue.append((current.left, level + 1))
            if current.right:
                queue.append((current.right, level + 1))


        for lists in d.values():

            x = sorted(lists)
            count = 0
            for i in range(len(lists)):
                if lists[i] != x[i]:
                    j = lists.index(x[i])
                    lists[i], lists[j] = lists[j], lists[i]
                    count += 1
            result += count


        return result
```
