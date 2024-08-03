# [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)

You are given an array `prices` where `prices[i]` is the price of a given stock on the `ith` day.

You want to `maximize` your `profit` by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum `profit` you can achieve from this transaction. If you cannot achieve any profit, return `0`.
### Example

**Input:** `prices = [7,1,5,3,6,4]`  
**Output:** `5` 
**Explanation:** Buy on day `2` `(price = 1)` and sell on day `5` `(price = 6)`, `profit = 6-1 = 5`.

## Intuition

The problem aims to find the maximum profit that can be obtained by buying and selling a stock. The given solution seems to follow a simple approach of iterating through the prices, keeping track of the minimum buying price, and updating the profit whenever a higher selling price is encountered.


## Code

```C++
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int n=prices.size(),mini=prices[0],profit=0;
        for(int i=1; i<n; i++){
            int cost=prices[i]-mini;
            profit=max(profit,cost);
            mini=min(mini,prices[i]);
        }
        return profit;
    }
};
```

## Complexity

- **Time Complexity:** O(N)  
  We iterate through the array once, where `N` is the length of the array.

- **Space Complexity:** O(1)  
We are using constant extra space.

---
