# LeetCode 189 - Rotate Array

## 🔗 LeetCode Link

https://leetcode.com/problems/rotate-array/

---

## 📄 Problem Statement

Given an integer array **nums**, rotate the array to the **right by k steps**, where **k is non-negative**.

The rotation must be done **in-place**, meaning you cannot use another array for storing the result.

---

## Example

Input
nums = [1,2,3,4,5,6,7], k = 3

Output
[5,6,7,1,2,3,4]

Explanation
Rotate the array to the right by **3 steps**:

Step 1 → [7,1,2,3,4,5,6]
Step 2 → [6,7,1,2,3,4,5]
Step 3 → [5,6,7,1,2,3,4]

---

## 💡 Approach

To solve this problem efficiently, we use the **Array Reversal Technique**.

Steps:

1. Reverse the entire array.
2. Reverse the first **k elements**.
3. Reverse the remaining **n − k elements**.

This rotates the array without using extra space.

---

## 🧠 Java Solution

```java
class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length;

        k = k % n;

        reverse(nums, 0, n - 1);
        reverse(nums, 0, k - 1);
        reverse(nums, k, n - 1);
    }

    public void reverse(int[] nums, int start, int end) {
        while (start < end) {
            int temp = nums[start];
            nums[start] = nums[end];
            nums[end] = temp;

            start++;
            end--;
        }
    }
}
```

---

## ⏱ Time Complexity

O(n)

We reverse the array elements a constant number of times.

---

## 📦 Space Complexity

O(1)

No extra space is used since the rotation is done **in-place**.
