# Largest Number At Least Twice of Others
You are given an integer array nums where the largest integer is unique.

Determine whether the largest element in the array is at least twice as much as every other number in the array. If it is, return the index of the largest element, or return -1 otherwise.

### Solution :smile:
```java
class Solution {
    public int dominantIndex(int[] nums) {
        int max = 0;
        int index = 0;
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] > max) {
                max = nums[i];
                index = i;
            }
        }
        
        for (int i = 0; i < nums.length; i++) {
            if (i == index) continue;
            if (nums[i] * 2 > max) return -1;
        }
        
        return index;
    }
}
```
