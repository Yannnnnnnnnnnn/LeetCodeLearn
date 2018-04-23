Link
---
https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/description/

Part Mine Code
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
    
    TreeNode* sortedArrayToBST(vector<int>& nums) {
        return buildBSTree(nums, 0, nums.size() - 1);
    }
    
    TreeNode* buildBSTree(vector<int>& num, int start, int end) 
    {
        if (start <= end) 
        {
            int mid = (start + end) / 2;
            TreeNode *left = buildBSTree(num, start, mid - 1);
            TreeNode *right = buildBSTree(num, mid + 1, end);
            TreeNode *node = new TreeNode(num[mid]);
            node->left = left;
            node->right = right;
            return node;
        }
        return NULL;
}
};
```
