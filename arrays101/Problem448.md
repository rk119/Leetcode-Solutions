# Find All Numbers Disappeared in an Array
Given an array nums of n integers where nums[i] is in the range [1, n], return an array of all the integers in the range [1, n] that do not appear in nums.

### Solution :smile:
```java
class Solution {
    public List<Integer> findDisappearedNumbers(int[] nums) {
        for (int i = 0; i < nums.length; i++) {
            while (nums[i] != i + 1 && nums[i] != nums[nums[i] - 1]) {
                int tmp = nums[i];
                nums[i] = nums[tmp - 1];
                nums[tmp - 1] = tmp;
            }
        }     
        
        List<Integer> result = new ArrayList<Integer>();
        for (int i = 0; i < nums.length; i++) { 
            if (nums[i] != i + 1)
                result.add(i+1);
        }
        
        return result;
    }
}
```
