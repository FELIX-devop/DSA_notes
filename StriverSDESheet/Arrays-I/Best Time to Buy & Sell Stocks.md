# Best Time to Buy and Sell Stock

## Problem
You are given an array `prices` where `prices[i]` is the price of a given stock on the `i`th day.  
You want to maximize your profit by choosing **a single day to buy** one stock and choosing **a different day in the future to sell** that stock.

Return the maximum profit you can achieve from this transaction.  
If you cannot achieve any profit, return `0`.

(LeetCode Problem No: **121**)

### Input
prices = [7,1,5,3,6,4]

### Output
5

## Approach
- `minPrice` variable-la ippo varaikkum lowest price-ah store pannum  
- `maxProfit` variable-la maximum profit-ah track pannum  
- Array full-ah iterate pannum  
- Current price `minPrice`-vida kammi-na, `minPrice` update pannum  
- Illatti, current price-la sell panna profit calculate pannum  
- Andha profit `maxProfit`-vida perusa irundhaa update pannum  

## Code
```java
class Solution {
    public int maxProfit(int[] prices) {
        int maxProfit = 0;
        int minPrice = Integer.MAX_VALUE;

        for(int i = 0; i < prices.length; i++){
            if(prices[i] < minPrice){
                minPrice = prices[i];
            }
            else{
                int profit = prices[i] - minPrice;
                if(profit > maxProfit){
                    maxProfit = profit;
                }
            }
        }
        return maxProfit;
    }
}