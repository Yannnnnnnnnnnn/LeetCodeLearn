Link
---
https://leetcode.com/problems/roman-to-integer/description/

Mine Code
---
```
class Solution {
public:
    int romanToInt(string s) {
        std::map<char,int> roman_int;
        roman_int['D']=500;
        roman_int['L']=50;
        roman_int['V']=5;
        roman_int['M']=1000;
        roman_int['C']=100;
        roman_int['X']=10;
        roman_int['I']=1;
        int result = roman_int[s[0]];
        for(int i=1;i<s.size();i++)
        {
            result += roman_int[s[i]];
            if(roman_int[s[i]]>roman_int[s[i-1]])
                result -= 2*roman_int[s[i-1]];
        }
        
        return result;
    }
};
```
