# 102.-Binary-Tree-Level-Order-Traversal


`````py
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        q = collections.deque()
        q.append(root)
        ans = []

        while q:
            temp = [] # for each level, it will add new temp list and update in ans
            for i in range(len(q)):
                cur = q.popleft()
                if cur:
                    temp.append(cur.val)
                    q.append(cur.left)
                    q.append(cur.right)
            if temp:
                ans.append(temp)
        return ans 

`````
