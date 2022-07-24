# Pascal's Triangle
Given an integer numRows, return the first numRows of Pascal's triangle.

### Solution :smile:
```java
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> result = new ArrayList<>();
        result.add(List.of(1));
        if (numRows == 1) return result;
        
        for (int i = 1; i < numRows; i++) {
            List<Integer> temp = new ArrayList<>();
            temp.add(1);
            
            for (int j = 1; j < i; j++) 
                temp.add(result.get(i-1).get(j-1) + result.get(i-1).get(j));
            
            temp.add(1);

            result.add(temp);
        }
        return result;
    }
}
```
