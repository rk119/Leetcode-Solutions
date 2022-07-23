# Third Maximum Number
Given an integer array nums, return the third distinct maximum number in this array. If the third maximum does not exist, return the maximum number.

### Solution :smile:
```java
class Solution {
    public int thirdMax(int[] nums) {
        if (nums.length < 2) return nums[0];
        
        Integer firstMax = null, secondMax = null, thirdMax = null;
        
        for (Integer num : nums) {
            if (num.equals(firstMax) || num.equals(secondMax) || num.equals(thirdMax)) continue;
            
            if (firstMax == null || num > firstMax) {
                thirdMax = secondMax;
                secondMax = firstMax;
                firstMax = num;
                
            } else if (secondMax == null || num > secondMax) {
                thirdMax = secondMax;
                secondMax = num;
                
            } else if (thirdMax == null || num > thirdMax) {
                thirdMax = num;
            }
        }
        return thirdMax == null ? firstMax : thirdMax;
    }
}
```
