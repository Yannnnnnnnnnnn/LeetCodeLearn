Link
---
https://leetcode.com/problems/same-tree/description/

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
    bool compareNode(TreeNode *p, TreeNode *q)
    {
        if(p!=NULL && q!=NULL)
        {
            if(p->val==q->val)
            {
                return compareNode(p->left,q->left) && compareNode(p->right,q->right); 
            }
            else
            {
                return false;
            }
        }
        if(p==NULL && q==NULL)
        {
            return true;           
        }
        if( (p==NULL && q!=NULL) || (p!=NULL && q==NULL))
        {
            return false;           
        }
        
        return false;

    }
    bool isSameTree(TreeNode* p, TreeNode* q) {
        return compareNode(p,q);
    }
};
```
