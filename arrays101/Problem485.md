# Max Consecutive Ones
Given a binary array nums, return the maximum number of consecutive 1's in the array.

### Solution :smile:
```java
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int count = 0, max = Integer.MIN_VALUE;
        for (int num : nums) {
            if (num == 1)
                count++;
            else if (num != 1) {
                max = Math.max(max, count);
                count = 0;
            }
        }
        
        max = Math.max(max, count); 
        return max;
    }
}
```
