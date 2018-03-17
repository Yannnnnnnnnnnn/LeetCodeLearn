Link
---
https://leetcode.com/problems/longest-substring-without-repeating-characters/description/

Mine Code
---
```
class Solution {
public:
    int lengthOfLongestSubstring(string s) 
    {
        if(s.size()<=1)
        {
            return s.size();
        }
        
        set<char> max_length(s.begin(),s.end());

        for(int i=max_length.size();i>0;i--)
        {
            for(int j=0;j<=(s.size()-i);j++)
            {
                set<char> length(s.begin()+j,s.begin()+j+i);

                if(length.size()==i)
                {
                    return i;
                }
            }
        }
    }
};
```
