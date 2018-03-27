Link
---
https://leetcode.com/problems/count-and-say/description/

Mine Code
---
```
class Solution {
public:
    string countAndSay(int n) {
        string result = "1";
        stringstream ss;
        string str;

        for(int i=0;i<n-1;i++)
        {
            string temp = "";
            char current = result[0];
            int count = 1;
            int index = 1;
            while(index<result.size())
            {
                if(current==result[index])
                {
                    
                    count++;
                }
                else
                {
                    count = count*10 + atoi(&current);
                    ss.clear();
                    ss<<count;
                    ss>>str;
                    temp = temp + str;
                    
                    current = result[index];
                    count = 1;
                }
                index++;
                
            }
            count = count*10 + atoi(&current);
            ss.clear();
            ss<<count;
            ss>>str;
            temp = temp + str;
            result = temp;
            
        }
        
        return result;
    }
};
```
