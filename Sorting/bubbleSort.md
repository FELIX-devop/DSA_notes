# Bubble Sort

## Problem
Given an integer array, sort the array in ascending order using **Bubble Sort** algorithm.

### Input
arr = [4,3,2,1]

### Output
[1,2,3,4]

## Approach
- Array full-ah multiple passes-la iterate pannum  
- Adjacent elements-ah compare pannum  
- Left element perusa irundhaa, right element-oda **swap** pannum  
- Ovvoru pass mudincha apram, largest element end-ku move aagum  
- Indha process ellaa elements sort aagura varaikum repeat pannum  

## Code
```java
import java.util.Arrays;

public class bubbleSort {
    public static void main(String[] args) {
        int[] arr = {4,3,2,1};
        for (int i = 0; i < arr.length; i++) {
            for(int j = 0; j < arr.length - 1 - i; j++){
                if(arr[j] > arr[j + 1]){
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
        System.out.println(Arrays.toString(arr));
    }
}