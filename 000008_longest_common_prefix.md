Link
---
https://leetcode.com/problems/longest-common-prefix/description/

Mine Code
---
```
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        string result = "";
        
        if(strs.size()==0 || strs[0].size()==0)
        {
            return result;
        }
        
        
        for(int i = 0;i<strs[0].size();i++)
        {
            int prefix_size =  1;
            for(int j=1;j<strs.size();j++)
            {
                if(strs[0][i]!=strs[j][i])
                {
                    return result;
                }
                prefix_size++;  
            }
            
            if(prefix_size==strs.size())
            {
                result += strs[0][i];
            }
        }
        
        return result;
    }
};
```
