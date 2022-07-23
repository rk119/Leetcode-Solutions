# Height Checker
A school is trying to take an annual photo of all the students. The students are asked to stand in a single file line in non-decreasing order by height. Let this ordering be represented by the integer array expected where expected[i] is the expected height of the ith student in line.

You are given an integer array heights representing the current order that the students are standing in. Each heights[i] is the height of the ith student in line (0-indexed).

Return the number of indices where heights[i] != expected[i].

### Solution :smile:
```java
class Solution {
    public int heightChecker(int[] heights) {
        if (heights == null || heights.length < 1) return 0;
        
        int[] heightFreq = new int[101];
        
        for (int height : heights) 
            heightFreq[height]++;
        
        int count = 0;
        for (int i = 0, currentHeight = 0; i < heights.length; i++) {
            while (heightFreq[currentHeight] == 0) currentHeight++;
            
            if (currentHeight != heights[i]) count++;
            
            heightFreq[currentHeight]--; 
        }
        
        return count;
    }
}
```
