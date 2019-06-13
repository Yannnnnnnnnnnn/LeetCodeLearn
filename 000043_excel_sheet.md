Link
---
https://leetcode.com/problems/excel-sheet-column-title/description/

Not Mine Code
---
```
class Solution {
public:
    string convertToTitle(int n) {
        string s;
        while (n > 0) {
            n -= 1;
            s = static_cast<char>('A' + n%26) + s;
            n /= 26;
        }
        return s;
    }
};
```

Mine Code
---
```
class Solution {
public:
    int titleToNumber(string s) {
        int sum = 0;
        double plus26 = 1;
        int intA = int('A')-1;
        for(int i=s.size()-1;i>=0;i--)
        {
            sum += (int(s[i])-intA)*plus26;
            plus26 *=26;
        }
        
        return sum;
    }
};
```
