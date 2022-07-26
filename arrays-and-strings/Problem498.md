# Diagonal Traverse

Given an m x n matrix mat, return an array of all the elements of the array in a diagonal order.

### Solution :smile:

```java
class Solution {
    public int[] findDiagonalOrder(int[][] mat) {
        int numOfRows = mat.length;
        int numOfCols = mat[0].length;
        
        int[] result  = new int[numOfRows * numOfCols];
        int row = 0;
        int col = 0;
        
        for (int i = 0; i < (numOfRows * numOfCols); i++) {
            result[i] = mat[row][col];
            
            if ((row + col) % 2 == 0) {
                if (row - 1 >= 0 && col + 1 < numOfCols) {
                    row--;
                    col++;
                    
                } else if (col + 1 < numOfCols) 
                    col++;
    
                else 
                    row++;
                
            } else {
                if (row + 1 < numOfRows && col - 1 >= 0) {
                    row++;
                    col--;
                    
                } else if (row + 1 < numOfRows) 
                    row++;
                
                else col++;
            }
        }
        
        return result;
    }
}
```
