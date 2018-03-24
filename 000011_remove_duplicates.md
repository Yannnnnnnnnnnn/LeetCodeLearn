Link
---
https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/

Mine Code
```
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        
        if(nums.size()==0)
        {
            return 0;
        }
        
        int index = 1;
        int current = nums[0];
        for(int i=1;i<nums.size();i++)
        {
            if(current==nums[i])
            {
                continue;
            }
            if(current!=nums[i])
            {
                nums[index++] = nums[i];
                current = nums[i];
                continue;
            }
        }
        
        return index;
    }
};
```
