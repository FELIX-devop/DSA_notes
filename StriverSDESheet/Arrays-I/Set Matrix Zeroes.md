# Set matrix zero

## Problem
Note:if only matrix has 0 and 1.
input       output
1 1 1       1 0 1
1 0 1  ---> 0 0 0
1 1 1       1 0 1

## Approach
first array full ah traverse panitu zero irukura column and row lam -1 change pannaum.why from 1 to -1 not 0. from 1 to 0 mathuna next namma chnage panina 0 oda row colum affect agum.so -1 better.row and colum value chnage panna separate function use pandrathu better.last ah oru loop run pani -1 ellam 0 va change pannanum.

## Code
```java
(class Solution {
   
    public void setZeroes(int[][] matrix) {
        int row = matrix.length;
        int col = matrix[0].length;
        for(int i = 0;i<row;i++){
            for(int j = 0;j<col;j++){
               if(matrix[i][j]==0){
                changeRow(matrix,i);
                changeColumn(matrix,j);
               }
                 
            }
        }
        for(int i = 0;i<row;i++){
            for(int j = 0;j<col;j++){
               if(matrix[i][j]==-1){
                  matrix[i][j]=0;
               }
            }
        }
        
    }

    public static void changeRow(int[][] matrix,int num){
        int row = matrix.length;
        int col = matrix[0].length;
        for(int i=0;i<col;i++){
            if(matrix[num][i]!=0){
                matrix[num][i]=-1;
            }
        }
    }
    public static void changeColumn(int[][] matrix,int num){
        int row = matrix.length;
        int col = matrix[0].length;
        for(int i =0;i<row;i++){
            if(matrix[i][num]!=0){
                matrix[i][num]=-1;
            }

        }
    }

})
```


## Problem
Given an m x n integer matrix `matrix`, if an element is `0`, set its entire row and column to `0`s.
## Note
array la 0 and 1 ilama numbers iruntha.

### Input
matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]

### Output
[[0,0,0,0],[0,4,5,0],[0,3,1,0]]

## Approach
Rendu boolean array create pannum:  
- `rowMark` for rows  
- `colMark` for columns  

First loop-la matrix traverse panni, zero irukkura edathula corresponding row and column index-ku `true` nu mark pannum.  
Next loop-la, entha row illa column `true` ah irukko, antha position-la value-ah `0` nu set pannum.

## Code
```java
class Solution {
    public void setZeroes(int[][] matrix) {

        int row = matrix.length;
        int col = matrix[0].length;

        boolean[] rowMark = new boolean[row];
        boolean[] colMark = new boolean[col];

        // Step 1: mark rows & columns
        for(int i = 0; i < row; i++){
            for(int j = 0; j < col; j++){
                if(matrix[i][j] == 0){
                    rowMark[i] = true;
                    colMark[j] = true;
                }
            }
        }

        // Step 2: set zeroes
        for(int i = 0; i < row; i++){
            for(int j = 0; j < col; j++){
                if(rowMark[i] || colMark[j]){
                    matrix[i][j] = 0;
                }
            }
        }
    }
}
```

