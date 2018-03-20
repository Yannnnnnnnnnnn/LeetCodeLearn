Link
---
https://leetcode.com/problems/palindrome-number/description/

Mine Code
---
```
class Solution {
public:
    bool isPalindrome(int x) {
        if(x<0)
        {
            return false;
        }
        
        int result = 0;
        int orgin_value = x;
        while(x)
        {
            result = result*10 + x%10;
            x /= 10;
        } 

        if(orgin_value==result)
        {
            return true;
        }
        
        return false;
    }
};
```
