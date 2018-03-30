Link
---
https://leetcode.com/problems/length-of-last-word/description/

Mine Code
---
```
class Solution {
public:
    int lengthOfLastWord(string s) {
        int length = 0;
        int i = s.size()-1;
        while(s[i]==' ' && i>=0)
        {
            i--;
        }
        for(;i>=0;i--)
        {
            if(s[i]==' ')
            {
                return length;
            }
            else
            {
                length++;
                
            }
        }
        
        return length;
    }
};
```
