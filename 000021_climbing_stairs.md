Link
---
https://leetcode.com/problems/climbing-stairs/description/

Mine Code
---
```
class Solution {
public:
    int climbStairs(int n) {
        int max_two = n/2;
        int count = 1; // leave 1 1 1 1 ... 1 1 1 alone
        if(max_two==0)
        {
            return count;
        }
        int tot_number = n-1;
        double loc_count  = n-1; 
        for(int i=1;i<=max_two;i++)
        {   
            count += loc_count;
            loc_count = loc_count*(tot_number-i)*(tot_number-i-1)/(tot_number*(i+1));
            tot_number--;
        }
        return count;
    }
};
```
