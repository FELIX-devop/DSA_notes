# Rotate Image

## Problem
You are given an `n x n` 2D matrix representing an image.  
Rotate the image **90 degrees clockwise in-place**.

You must modify the input matrix directly.  
Do not allocate another 2D matrix.

(LeetCode Problem No: **48**)

### Input
matrix =  
[[1,2,3],  
 [4,5,6],  
 [7,8,9]]

### Output
[[7,4,1],  
 [8,5,2],  
 [9,6,3]]

## Approach
- First matrix-oda **transpose** find pannum  
  - `matrix[i][j]` ↔ `matrix[j][i]` swap pannum  
- Apram **ovvoru row-um reverse** pannum  
- Transpose + row reverse combine panna, matrix 90° clockwise rotate aagum  

## Code
```java
class Solution {
    public void rotate(int[][] matrix) {
        int n = matrix.length;

        // find the transpose of the matrix
        for(int i = 0; i < n - 1; i++){
            for(int j = i + 1; j < n; j++){
                int temp = matrix[i][j];
                matrix[i][j] = matrix[j][i];
                matrix[j][i] = temp;
            }
        }

        // reverse each row of the matrix
        for(int i = 0; i < n; i++){
            reverse(matrix[i]);
        }
    }

    public void reverse(int[] arr){
        int start = 0;
        int end = arr.length - 1;
        while(start < end){
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            start++;
            end--;
        }
    }
}