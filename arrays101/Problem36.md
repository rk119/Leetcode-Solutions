# Valid Sudoku
Determine if a 9 x 9 Sudoku board is valid. Only the filled cells need to be validated according to the following rules:

1) Each row must contain the digits 1-9 without repetition.
2) Each column must contain the digits 1-9 without repetition.
3) Each of the nine 3 x 3 sub-boxes of the grid must contain the digits 1-9 without repetition.

<bold>Note:</bold>
- A Sudoku board (partially filled) could be valid but is not necessarily solvable.
- Only the filled cells need to be validated according to the mentioned rules.
 

### Solution :smile:
```java
class Solution {
    public boolean isValidSudoku(char[][] board) {
        // row = 0, board[row][col] = 3, value = (3)0
        // col = 1, board[row][col] = 3, value = 1(3)
        // block = middle row and right col (1,2), board[row][col] = 3, value = 1(3)2

        Set exists = new HashSet();
        for (int row = 0; row < 9; row++){
            for (int col = 0; col < 9; col++) {
                if (board[row][col] != '.') {
                    String value = "(" + board[row][col] + ")";
                    if (!exists.add(value + row) || !exists.add(col+value) || !exists.add(row/3 + value + col/3))
                        return false;
                }
            }
        }
        return true;
    }
}
```
