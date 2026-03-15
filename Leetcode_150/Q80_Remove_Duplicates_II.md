# LeetCode 80 - Remove Duplicates from Sorted Array II

## 🔗 LeetCode Link

https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/

---

## 📄 Problem Statement

Given an integer array **nums** sorted in non-decreasing order, remove some duplicates **in-place** such that each unique element appears **at most twice**.

The relative order of the elements should be kept the same.

Return **k**, the number of elements after removing extra duplicates.

The first **k elements** of `nums` should contain the final result.

---

## Example

Input
nums = [1,1,1,2,2,3]

Output
[1,1,2,2,3]

Explanation
Each number can appear **at most two times**, so the extra `1` is removed.

---

## 💡 Approach

1. Use a pointer `i` to track the position to insert the next valid element.
2. Iterate through the array using a for-each loop.
3. If `i < 2`, we always add the element.
4. If `nums[i - 2] != num`, it means the element has appeared less than two times, so we keep it.
5. Otherwise, skip the element.

This ensures that every element appears **at most twice**.

---

## 🧠 Java Solution

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int i = 0;

        for (int num : nums) {
            if (i < 2 || nums[i - 2] != num) {
                nums[i] = num;
                i++;
            }
        }

        return i;
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

No extra space is used since the operation is done **in-place**.
