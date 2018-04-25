Link
---
https://leetcode.com/problems/path-sum/description/

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
    bool hasSum(TreeNode* root, int sum) {
        
        sum -= root->val;
        
        if(root->left==NULL && root->right==NULL)
        {
            if(sum==0)
            {
                return true;
            }
            else
            {
                return false;                
            }

        }
        
        bool result = false;
        
        if(root->left!=NULL)
        {
            result = hasSum(root->left,sum) ;
        }
        
        if(root->right!=NULL)
        {
            result = result||hasSum(root->right,sum);
        }
        
        return result;
        
    }
    bool hasPathSum(TreeNode* root, int sum) {
        
        if(root==NULL)
        {
            return false;

        }
        
        sum -= root->val;
        
        if(root->left==NULL && root->right==NULL)
        {
            if(sum==0)
            {
                return true;
            }
            else
            {
                return false;                
            }

        }
        
        bool result = false;
        
        if(root->left!=NULL)
        {
            result = hasSum(root->left,sum) ;
        }
        
        if(root->right!=NULL)
        {
            result = result||hasSum(root->right,sum);
        }
        
        return result;
        
        
        
    }
};
```
