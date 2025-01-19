2326. Spiral Matrix IV
https://leetcode.com/problems/spiral-matrix-iv/description/

PYTHON SOLUTION
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def spiralMatrix(self, m: int, n: int, head: Optional[ListNode]) -> List[List[int]]:


        # Initialize all elements of the matrix with -1
        matrix = [[-1] * n for _ in range(m)]

        directions = [(0, 1), (1, 0), (0, -1), (-1, 0)]

        k = 0

        direction = directions[0]

        i, j = 0, 0
        ni, nj = 0, 0

        # Function to check if an element is outside the matrix
        def is_outside(x, y):
            return not (x >= 0 and x < m and y >= 0 and y < n)

        # Iterate over the linked list nodes
        while head:

            x = head.val

            matrix[ni][nj] = x

            # Calculate next element in the matrix
            ni = i + direction[0]
            nj = j + direction[1]

            # Change direction if the next element of the matrix is invalid
            if is_outside(ni, nj) or matrix[ni][nj] != -1:
                k += 1
                direction = directions[k % 4]

                ni = i + direction[0]
                nj = j + direction[1]
            
            i = ni
            j = nj

            # Go to the next node
            head = head.next

        return matrix

```
