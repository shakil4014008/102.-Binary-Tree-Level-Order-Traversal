# 102.-Binary-Tree-Level-Order-Traversal


`````c#
Given a binary tree, return the level order traversal of its nodes' values. (ie, from left to right, level by level).

/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     public int val;
 *     public TreeNode left;
 *     public TreeNode right;
 *     public TreeNode(int val=0, TreeNode left=null, TreeNode right=null) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
public class Solution {
     
    
    
    public IList<IList<int>> LevelOrder(TreeNode root) {
         
        var result = new List<IList<int>>();
        if(root == null) return result;
        
        var queue = new Queue<TreeNode>();
        queue.Enqueue(root);
        
        while(queue.Any()){ // any is better for performance 
            
            var size = queue.Count;
            
            var oneResult = new List<int>();
            
            for(int i=0; i< size; i++){
                
                var cur = queue.Dequeue();
                oneResult.Add(cur.val);
                
                if(cur.left != null){
                    queue.Enqueue(cur.left);
                }
                
                if(cur.right != null){
                    queue.Enqueue(cur.right);
                }
            }
            
            result.Add(oneResult);
        }
        
        return result;
    
    } 
}

`````
