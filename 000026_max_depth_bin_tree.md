Link
---
https://leetcode.com/problems/maximum-depth-of-binary-tree/description/

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
    int countDepth(TreeNode *node_depth)
    {
        if(node_depth!=NULL)
        {
            return 1+max(countDepth(node_depth->left),countDepth(node_depth->right));
        }
        else
        {
            return 0;
        }
    }
        
    int maxDepth(TreeNode* root) {
        int max_depth = 0;
        if(root==NULL)
        {
            return max_depth;
        }
        else
        {
            max_depth=1;
            return max_depth+max(countDepth(root->left),countDepth(root->right));
        }
    }
};
```
