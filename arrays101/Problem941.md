# Valid Mountain Array
Given an array of integers arr, return true if and only if it is a valid mountain array.

### Solution :smile:
```java
class Solution {
    public boolean validMountainArray(int[] arr) {
        if (arr.length < 3) return false;

        int i = 0;
        while (i < arr.length && i + 1 < arr.length && arr[i] < arr[i+1]) 
            i++;
        
        if (i == 0 || i + 1 == arr.length) return false;
        
        while (i < arr.length && i + 1 < arr.length )
            if (arr[i] <= arr[i++ + 1]) return false;
        
        return true;
    }
}
```
