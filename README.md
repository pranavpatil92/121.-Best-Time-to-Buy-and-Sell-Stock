# Best Time to Buy and Sell Stock

**Difficulty:** Easy
**Topics:** Array, Dynamic Programming
**Link:** https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

## Problem

You are given an integer array `prices` where `prices[i]` is the price of a given stock on the `i`th day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return `0`.

### Example 1
```
Input: prices = [10,1,5,6,7,1]
Output: 6
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 7), profit = 7 - 1 = 6.
```

### Example 2
```
Input: prices = [10,8,7,5,2]
Output: 0
Explanation: In this case, no transactions are done and the max profit = 0.
```

### Constraints
- `1 <= prices.length <= 100`
- `0 <= prices[i] <= 100`

## Approach

One-pass, O(n) time, O(1) space.

Track two things while scanning left to right:
1. `minPrice` — the lowest price seen so far (best day to have bought).
2. `maxProfit` — the best profit seen so far (price today minus `minPrice`).

At each day, either a new minimum is found, or a new max profit is found — never both on the same day, since if today is a new low, selling today gives 0 profit.

## Complexity

- Time: O(n)
- Space: O(1)
