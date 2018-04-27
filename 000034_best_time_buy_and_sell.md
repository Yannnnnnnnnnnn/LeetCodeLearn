Link
---
https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/

Mine Code
---
```
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int max_profit = 0;
        for(int i=0;i<prices.size();i++)
        {
            for(int j=i+1;j<prices.size();j++)
            {
                int cur_profit = prices[j]-prices[i];
                if( cur_profit>max_profit )
                {
                    max_profit = cur_profit;
                }
            }
        }
        
        return max_profit;
    }
};
```
