# Largest Perimeter Triangle
Given an integer array nums, return the largest perimeter of a triangle with a non-zero area, formed from three of these lengths. If it is impossible to form any triangle of a non-zero area, return 0.

### Solution :smile:
```java
class Solution {
    public int largestPerimeter(int[] nums) {
        Arrays.sort(nums);
        int i = nums.length-3;
        
        while (i >= 0 && (nums[i] + nums[i+1] <= nums[i+2]))
            i--;
        
        if (i >= 0) 
            return (nums[i] + nums[i+1] + nums[i+2]);
        
        return 0;
    }
}
```
