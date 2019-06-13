Linke
---
https://leetcode.com/problems/factorial-trailing-zeroes/

Not Mine
---
```
class Solution {
public:
    int trailingZeroes(int n) {
       int res = 0;
       while(n > 0) res += (n = (n / 5));
       return res;
    }
};
```

Material
---
https://blog.csdn.net/taoyanqi8932/article/details/52129450
