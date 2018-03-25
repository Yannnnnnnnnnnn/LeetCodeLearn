Link
---
https://leetcode.com/problems/remove-element/description/

Mine Code
---
```
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        
        if(nums.size()==0)
        {
            return 0;
        }
        
        int current_index = 0;
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]!=val)
            {
                nums[current_index++] = nums[i];
            }
        }
        
        return current_index;
    }
};
```
