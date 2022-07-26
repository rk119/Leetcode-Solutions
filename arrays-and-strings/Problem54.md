# Spiral Matrix
Given an m x n matrix, return all elements of the matrix in spiral order.

### Solution :smile:

```java
class Solution {
    public List<Integer> spiralOrder(int[][] matrix) {
        int left = 0, right = matrix[0].length-1, top = 0, bottom = matrix.length-1;
        List<Integer> spiral = new ArrayList<Integer>();
        
        while(true) {
            for (int i = left; i <= right; i++) 
                spiral.add(matrix[top][i]);
            if (++top > bottom) break;
            
            for (int i = top; i <= bottom; i++)
                spiral.add(matrix[i][right]);
            if (--right < left) break;
                
            for (int i = right; i >= left; i--) 
                spiral.add(matrix[bottom][i]);
            if (--bottom < top) break;
                
            for (int i = bottom; i >= top; i--) 
                spiral.add(matrix[i][left]);
            if (++left > right) break;                
        }
        
        return spiral;
    }
}
```
