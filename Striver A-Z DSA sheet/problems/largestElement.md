# Largest Element in an Array

## Problem
Given an integer array, find and return the **largest element** present in the array.

### Input
arr = [6,3,4,66,3,5,7,3,55,4]

### Output
66

## Approach
- `max` variable-la initial-ah `Integer.MIN_VALUE` assign pannum  
- Array full-ah iterate pannum  
- Ovvoru element-um `max`-oda compare panni, perusa irundhaa update pannum  
- Last-la `max` value return pannum  

## Code
```java
public class Main {
    public static void main(String[] args) {
        int[] arr = {6,3,4,66,3,5,7,3,55,4};
        int ans = largestElement(arr);
        System.out.print(ans);
    }

    public static int largestElement(int[] arr){
        int max = Integer.MIN_VALUE;
        for(int i = 0; i < arr.length; i++){
            max = Math.max(max, arr[i]);
        }
        return max;
    }
}