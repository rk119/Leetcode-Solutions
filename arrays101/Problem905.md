# Sort Array By Parity
Given an integer array nums, move all the even integers at the beginning of the array followed by all the odd integers.

Return any array that satisfies this condition.

### Solution :smile:
```java
class Solution {
    public int[] sortArrayByParity(int[] nums) {
        if (nums.length > 1) {
            for (int i = 0, j = 0; i < nums.length; i++) {
                if (nums[i] % 2 == 0) {
                    int temp = nums[j];
                    nums[j++] = nums[i];
                    nums[i] = temp;
                }
            }
        }
        return nums;
    }
}
```
