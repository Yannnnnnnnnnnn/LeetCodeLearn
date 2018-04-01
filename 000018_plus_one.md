Link
---
https://leetcode.com/problems/plus-one/description/

Mine Code
---
```
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        int i = digits.size() - 1;
        int temp = 0;
        temp = digits[i] + temp + 1;
        digits[i--] = temp%10;
        temp /= 10;
        for(;i>=0;)
        {
            temp = digits[i] + temp;
            digits[i--] = temp%10;
            temp /= 10;
        }
        if(temp!=0)
        {
            digits.insert(digits.begin(),temp);
        }
        
        return digits;
    }
};
```
