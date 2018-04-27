Link
---
https://leetcode.com/problems/valid-palindrome/description/

Mine Code
---
```
class Solution {
public:
    bool characters(char c)
    {
        if( (c>='0' && c<='9') || (c>='A' && c<='Z') || (c>='a' && c<='z'))
        {
            return true;
        }
        
        return false;
    }
    bool isPalindrome(string s) {
        
        
        bool  no_character = false;
        for(int i=0;i<s.size();i++)
        {
            no_character = characters(s[i]);
            if(no_character)
                break;
        }
        
        if(!no_character)
        {
            return true;
        }
        
        int begin = 0;
        int end   = s.size()-1;
        
        while(begin<=end)
        {
            while(!characters(s[begin]))
            {
                begin++;
            }
            
            while(!characters(s[end]))
            {
                end--;
            }
            
            if(s[begin]!=s[end] && abs(s[begin]-s[end])!=32 )
            {
                return false;
            }
            
            if(abs(s[begin]-s[end])==32 && min(s[begin],s[end])<='9')
            {
                return false;
            }
            
            begin++;
            end--;
        }
        
        return true;
    }
};
```
