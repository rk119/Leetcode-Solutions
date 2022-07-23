# Find Numbers with Even Number of Digits
Given an array nums of integers, return how many of them contain an even number of digits.

### Solution :smile:
```java
class Solution {
    public int findNumbers(int[] nums) {
        int evens = 0;
        // for (int num : nums) {
        //     int count = 0;
        //     while (num > 0) {
        //         num /= 10;
        //         count++;
        //     }
        //     if (count % 2 == 0) evens++;
        // }
        
        for (int num : nums) {
            if ((num > 9 && num < 100) || (num > 999 && num < 10000) || num == 100000) {
                evens++;
            }
        }
        return evens;
    }
}
```
