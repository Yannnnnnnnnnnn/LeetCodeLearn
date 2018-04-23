Link
---
https://leetcode.com/problems/binary-tree-level-order-traversal-ii/description/

Mine Code
---
```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */

class Solution {
public:
    vector<vector<int>> levelOrderBottom(TreeNode* root) {
        vector<vector<int>> result;
        queue<TreeNode*> walking_queue;
        
        if(root==NULL)
        {
            return result;
        }
        
        walking_queue.push(root);
        
        while(!walking_queue.empty())
        {
            vector<int> current_layer_result;
            
            int current_layer_node_size = walking_queue.size();
            
            
            for(int i=0;i<current_layer_node_size;i++)
            {
                TreeNode* current_node = walking_queue.front();
                walking_queue.pop();
                current_layer_result.push_back(current_node->val);
                
                if(current_node->left!=NULL)
                {
                    walking_queue.push(current_node->left);
                }
                if(current_node->right!=NULL)
                {
                    walking_queue.push(current_node->right);
                }
                
            }
            
            result.push_back(current_layer_result);
    
            
        }
        
        reverse (result.begin( ), result.end( ) );
        
        return result;
    }
};
```
