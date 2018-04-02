Link
---
https://leetcode.com/submissions/detail/148066785/

Mine Code
---
```
class Solution {
public:
    string addBinary(string a, string b) {
        
        string result = a.size()>=b.size() ? a : b;
        
        int r_index = result.size()-1;
        int a_index = a.size()-1;
        int b_index = b.size()-1;
        
        char temp = '0';

        while(r_index>=0)
        {
            int count = 0;
            if(temp=='1')
                count++;
            if(a_index>=0 && a[a_index--]=='1')
                count++;
            if(b_index>=0 && b[b_index--]=='1')
                count++;
            
            if(count==0)
            {
                result[r_index] = '0';
                temp = '0';
            }
            if(count==1)
            {
                result[r_index] = '1';
                temp = '0';
            }
            if(count==2)
            {
                result[r_index] = '0';
                temp = '1';
            }
            if(count==3)
            {
                result[r_index] = '1';
                temp = '1';
            }
            r_index--;
        }
        
        if(temp=='1')
        {
            result.insert(result.begin(),'1');
        }
        
        return result;
    }
};
```
