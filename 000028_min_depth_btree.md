Link
---
https://leetcode.com/problems/minimum-depth-of-binary-tree/description/

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
    int depth(TreeNode *node)
    {
        if(node==NULL)
        {
            return 0;
        }
        if(node->left==NULL || node->right==NULL)
        {
            return max(depth(node->left),depth(node->right))+1;
        }
        return min(depth(node->left),depth(node->right))+1;
    }
    int minDepth(TreeNode* root) {
        if(root==NULL)
        {
            return 0;
        }
        if(root->left==NULL || root->right==NULL)
        {
            return max(depth(root->left),depth(root->right))+1;
        }
        return min(depth(root->left),depth(root->right))+1;
    }
};
```
