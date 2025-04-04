# Stock Buy and Sell – Max one Transaction Allowed


```cpp
class Solution {
  public:
    int maximumProfit(vector<int> &prices) {
        int buyprice=prices[0];
        int maxprofit=0;
        
        for(int i=0;i<prices.size();i++)
        {
            if(prices[i]>buyprice)
            {
                maxprofit=max(maxprofit,prices[i]-buyprice);
            }
            else
            {
                buyprice=prices[i];
            }
        }
        
        return maxprofit;
    }
};

```
