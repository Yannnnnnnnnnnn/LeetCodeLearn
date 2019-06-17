Link
---
https://leetcode.com/problems/rotate-array/


Mine Code
---

```
class Solution {
public:
    int getIndex(int length,int move,int index)
    {
        int result = 0;
        
        if(index<move)
        {
            result = length - move + index;
        }
        else
        {
            result = index - move;
        }
        
        
        if(result>length)
        {
           result -= length;
        }
        
        return result;
    }
    
    void rotate(vector<int>& nums, int k) {
        int nums_size = nums.size();
        int delta_k   = k%nums_size;
        
        vector<int> rotate_nums;
        
        for(int i=0;i<nums_size;i++)
        {
            rotate_nums.push_back(nums[getIndex(nums_size,delta_k,i)]);
        }
        
        nums.assign(rotate_nums.begin(),rotate_nums.end());
    }
};
```
