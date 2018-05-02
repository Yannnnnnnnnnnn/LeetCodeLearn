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
