# LeetCode 169 - Majority Element

## 🔗 LeetCode Link

https://leetcode.com/problems/majority-element/

---

## 📄 Problem Statement

Given an array **nums** of size **n**, return the **majority element**.

The **majority element** is the element that appears **more than ⌊n / 2⌋ times**.

You may assume that the majority element **always exists** in the array.

---

## Example

Input
nums = [3,2,3]

Output
3

Explanation
The number **3 appears more than n/2 times**, so it is the majority element.

---

Input
nums = [2,2,1,1,1,2,2]

Output
2

Explanation
The number **2 appears more than n/2 times**, so it is the majority element.

---

## 💡 Approach (Boyer-Moore Voting Algorithm)

1. Start with `count = 0` and `candidate = 0`.
2. Traverse the array.
3. If `count == 0`, set the current number as the candidate.
4. If the number is the same as the candidate, increase the count.
5. Otherwise, decrease the count.
6. At the end, the candidate will be the majority element.

This works because the majority element appears **more than half of the array size**.

---

## 🧠 Java Solution

```java
class Solution {
    public int majorityElement(int[] nums) {
        int count = 0;
        int candidate = 0;

        for (int num : nums) {
            if (count == 0) {
                candidate = num;
            }

            if (num == candidate) {
                count++;
            } else {
                count--;
            }
        }

        return candidate;
    }
}
```

---

## ⏱ Time Complexity

O(n)

We traverse the array only once.

---

## 📦 Space Complexity

O(1)

No extra space is used.
