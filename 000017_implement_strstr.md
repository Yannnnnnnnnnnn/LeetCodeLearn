Link
---
https://leetcode.com/problems/implement-strstr/description/

Mine Code
```
class Solution {
public:
    int strStr(string haystack, string needle) {
     
        if(haystack.size()<needle.size() )
        {
            return -1;
        }
        
        if( haystack==needle)
        {
            return 0;
        }
        
        for(int i=0;i<haystack.size()-needle.size()+1;i++)
        {
            int count = 0;
            for(int j=0;j<needle.size();j++)
            {
                if(haystack[i+j]!=needle[j])
                {
                    break;
                }
                else
                {
                    count++;
                }

            }
            if(count==needle.size())
            {
                return i;
            }
        }
        
        return -1;
    }
};
```
