# Minimum Size Subarray Sum

Given an array of positive integers nums and a positive integer target, return the minimal length of a contiguous subarray [nums<sub>l</sub>, nums<sub>l+1</sub>, ..., nums<sub>r-1</sub>, nums<sub>r</sub>] of which the sum is greater than or equal to target. If there is no such subarray, return 0 instead.

### Solution :smile:

```java
class Solution {
    public int minSubArrayLen(int target, int[] nums) {
        int minLength = Integer.MAX_VALUE, sum = 0;
        for (int right = 0, left = 0; right < nums.length; right++) {
            sum += nums[right];
            
            while (sum >= target) {
                minLength = (right - left + 1) < minLength ? (right - left + 1) : minLength;
                sum -= nums[left++];
            }
        }
        return (minLength == Integer.MAX_VALUE) ? 0 : minLength;
    }
}
```
