# Move Zeroes
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

### Solution :smile:
```java
class Solution {
    public void moveZeroes(int[] nums) {
        if (nums.length > 1) {
            for (int right = 0, left = 0; right < nums.length; right++) {
                if (nums[right] != 0) {
                    int temp = nums[left];
                    nums[left++] = nums[right];
                    nums[right] = temp;
                }
            }
        }
    }
}
```
