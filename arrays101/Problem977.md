# Squares of a Sorted Array
Given an integer array nums sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.

### Solution :smile:
```java
class Solution {
    public int[] sortedSquares(int[] nums) {
        int[] result = new int[nums.length];
        for (int  i = 0, j = nums.length-1, x = nums.length-1; x >= 0; x--) {
            if (Math.abs(nums[i]) > Math.abs(nums[j])) {
                result[x] = Math.abs(nums[i] * nums[i]);
                i++;
            } else {
                result[x] = Math.abs(nums[j] * nums[j]);
                j--;
            }
        }
        return result;
    }
}
```
