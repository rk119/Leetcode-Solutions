#  Replace Elements with Greatest Element on Right Side
Given an array arr, replace every element in that array with the greatest element among the elements to its right, and replace the last element with -1.

After doing so, return the array.

### Solution :smile:
```java
class Solution {
    public int[] replaceElements(int[] arr) {
        int max = -1;
        int temp ;
        
        for(int i = arr.length-1; i > -1; i--) {
            temp = arr[i];
            arr[i] = max;
            
           max = max < temp ? temp : max;
        }
        return arr;
    }
}
```
