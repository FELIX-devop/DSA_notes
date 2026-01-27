# Pascal Triangle

## Problem
Pascal Triangle-la 3 different type of problems irukkum.

1. Given row and column, antha specific element-ah find pannum  
2. Given row number, antha complete row-ah print pannum  
3. Given N, complete Pascal Triangle-ah form pannum  

### Input
Row, Column values illa N value (problem type-ku depend aagum)

### Output
1. Specific element value  
2. Given row  
3. Complete Pascal Triangle up to N rows  

## Approach
Indha moonu problem-kum base approach **NCR formula** dhaan.
 nCr =n!/r! * (n-r)1.
 

- Element find panna: `nCr` use pannum  
- Row print panna: same row-ku ella column values-um `nCr` use panni calculate pannum  
- Triangle form panna: 0 to N rows varaikum nested loop-la `nCr` apply pannum  

## Code 1
```java
  

public class Main {
    public static void main(String[] args) {
        int ans = nCr(6,4);
        System.out.print(ans);
        int[] arr = printPascalRow(6);
        System.out.print(Arrays.toString(arr));
        List<List<Integer>> list = printPascalTriangle(6);
        System.out.print(list);
    }
    
    
    public static int nCr(int n, int r){
        int res=1;
        n = n-1;
        r = r-1;
        for(int i=0;i<r;i++){
            res = res * (n-i);
            res = res / (i+1);
        }
        return res;
    }
    
    public static int[] printPascalRow(int num){
        int[] row = new int[num];
        for(int i =0;i<num;i++){
            row[i] = nCr(num,i+1);
        }return row;
    }
    public static List<List<Integer>> printPascalTriangle(int num){
         List<List<Integer>> list = new ArrayList<>();
         for(int i=1;i<=num;i++){
             List<Integer> row = new ArrayList<>();
             for(int j=1;j<=i;j++){
                row.add(nCr(i,j));
             }list.add(row);
         }
         return list;    
    }
}
    