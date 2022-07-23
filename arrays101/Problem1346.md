# Check If N and Its Double Exist
Given an array arr of integers, check if there exists two integers N and M such that N is the double of M ( i.e. N = 2 * M).

More formally check if there exists two indices i and j such that :

-> i != j

-> 0 <= i, j < arr.length

-> arr[i] == 2 * arr[j]

### Solution :smile:
```java
class Solution {
    public boolean checkIfExist(int[] arr) {
        Set<Integer> hs = new HashSet<Integer>();    
        if(arr[0] == 0) return true;
        hs.add(arr[0]);  
        
        for(int i = 1; i < arr.length; i++) {  
            // if twice of a number is present, we can return true  
            if(hs.contains(2 * arr[i])) return true;  
  
            // if the half of a number is present we have to ensure that  
            // the number is even  
            if(arr[i] % 2 == 0 && hs.contains(arr[i] / 2)) return true;  
  
            // add the number and move to the next iteration  
            hs.add(arr[i]);  
        }  
  
        return false; 
    }
}
```
