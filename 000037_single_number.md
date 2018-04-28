Link
---
https://leetcode.com/problems/single-number/description/

Mine Code
---
```
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        if(nums.size()<1)
        {
            return 0;
        }
        
        map<int,int> appear_count;
        
        for(int i=0;i<nums.size();i++)
        {
            auto iter = appear_count.find(nums[i]);
            if(iter==appear_count.end())
            {
               appear_count[nums[i]]=1;
            }
            else
            {
                appear_count[nums[i]]++;
            }
        }
        
        for(auto iter=appear_count.begin();iter!=appear_count.end();iter++)
        {
            if(iter->second==1)
            {
                return iter->first;
            }
        }
    }
};
```
