# Pascal's Triangle II
Given an integer rowIndex, return the rowIndex<sup>th</sup> (0-indexed) row of the Pascal's triangle.

### Solution :smile:
```java
class Solution {
    public List<Integer> getRow(int rowIndex) {
        long val = 1;
        List<Integer> result = new ArrayList<Integer>();
        
        for (int i = 0; i <= rowIndex; i++) {
            result.add((int) val);
            val = (val * (rowIndex-i)) / (i+1);
        }
        
        return result;
    }
}
```
