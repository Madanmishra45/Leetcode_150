# LeetCode 27 - Remove Element

## 🔗 LeetCode Link
https://leetcode.com/problems/remove-element/

---

## 📝 Problem Statement
Given an integer array nums and an integer val, remove all occurrences of val in-place and return the number of elements not equal to val.

The order of elements may change. The first k elements of nums should contain the elements which are not equal to val.

---

## 💡 Approach / Explanation
We use a pointer `k` to track the position where the next valid element should be placed.

Steps:
1. Traverse the array using a loop.
2. If the element is not equal to `val`, place it at index `k`.
3. Increase `k`.
4. Continue until the end of the array.

This shifts all valid elements to the front.

Time Complexity: **O(n)**  
Space Complexity: **O(1)**

---

## 💻 Solution (Java)

```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int k = 0;

        for(int i = 0; i < nums.length; i++){
            if(nums[i] != val){
                nums[k] = nums[i];
                k++;
            }
        }

        return k;
    }
}