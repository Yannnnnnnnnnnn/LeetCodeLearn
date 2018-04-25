Link
---
https://leetcode.com/problems/pascals-triangle/description/

Mine Code
---
```
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> result;
        
        // 0
        if(numRows>=1)
        {
            vector<int> first;
            first.push_back(1);
            result.push_back(first);
        }
        
        // 1
        if(numRows>=2)
        {
            vector<int> second;
            second.push_back(1);
            second.push_back(1);
            result.push_back(second);
        }
        
        // 2+
        for(int i=3;i<=numRows;i++)
        {
            vector<int> last;
            last.reserve(i);
            last.push_back(1);
            
            for(int j=2;j<=i-1;j++)
            {
                last.push_back( result[i-2][j-2] + result[i-2][j-1]);
            }
            
            last.push_back(1);
            
            result.push_back(last);
            
        }
        
        return result;
    }
};
```
