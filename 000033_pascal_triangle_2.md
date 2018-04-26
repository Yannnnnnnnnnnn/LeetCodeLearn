Link
---
https://leetcode.com/problems/pascals-triangle-ii/description/

Mine Code
---
```
class Solution {
public:
    vector<int> getRow(int rowIndex) {
        
        
        vector<int> result;
        result.reserve(rowIndex+1);
        
        vector<int> temp;
        for(int i=1;i<rowIndex;i++)
        {
            temp.push_back(i);
        }
        
        // First
        result.push_back(1);
           
        // Second
        if(rowIndex>=1)
            result.push_back(rowIndex);
        
        for(int i=rowIndex-1;i>1;i--)
        {
            int sum = 0;
            for(int j=0;j<i;j++)
            {
                sum += temp[j];
            }
            result.push_back(sum);
            
            for(int j=1;j<rowIndex;j++)
            {
                temp[j] += temp[j-1];
            }
        }
        
        // Last
        if(rowIndex>=2)
            result.push_back(1);
        
        return result;
    }
};
```
