# LeetCode 121 - Best Time to Buy and Sell Stock

## 🔗 LeetCode Link

https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

---

## 📄 Problem Statement

You are given an array **prices** where `prices[i]` is the price of a given stock on the **i-th day**.

You want to **maximize your profit** by choosing:

* One day to **buy** one stock
* A different day in the future to **sell** that stock

Return the **maximum profit** you can achieve from this transaction.

If you cannot achieve any profit, return **0**.

---

## Example

Input
prices = [7,1,5,3,6,4]

Output
5

Explanation
Buy on day **2 (price = 1)**
Sell on day **5 (price = 6)**

Profit = **6 - 1 = 5**

---

Input
prices = [7,6,4,3,1]

Output
0

Explanation
Prices keep decreasing, so **no profit is possible**.

---

## 💡 Approach

We track:

* **Minimum price** seen so far
* **Maximum profit** possible

Steps:

1. Initialize `minPrice` as the first element.
2. Traverse the array.
3. Update the minimum price if a smaller price is found.
4. Calculate profit = current price − minimum price.
5. Update maximum profit if the new profit is larger.

---

## 🧠 Java Solution

```java
class Solution {
    public int maxProfit(int[] prices) {
        int minPrice = Integer.MAX_VALUE;
        int maxProfit = 0;

        for (int price : prices) {

            if (price < minPrice) {
                minPrice = price;
            }

            int profit = price - minPrice;

            if (profit > maxProfit) {
                maxProfit = profit;
            }
        }

        return maxProfit;
    }
}
```

---

## ⏱ Time Complexity

O(n)

We traverse the array once.

---

## 📦 Space Complexity

O(1)

No extra space is used.
