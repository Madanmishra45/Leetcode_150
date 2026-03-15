# LeetCode 26 - Remove Duplicates from Sorted Array

## 🔗 LeetCode Link
https://leetcode.com/problems/remove-duplicates-from-sorted-array/

---

## 📄 Problem Statement

Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once.

---

## 💡 Approach

1. Use two pointers.
2. One pointer tracks unique elements.
3. If a new element is different, move it forward.

---

## 🧠 Java Solution

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int i = 0;

        for(int j = 1; j < nums.length; j++){
            if(nums[i] != nums[j]){
                i++;
                nums[i] = nums[j];
            }
        }

        return i + 1;
    }
}