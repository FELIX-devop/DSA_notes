# Selection Sort

## Problem
Given an integer array, sort the array in ascending order using **Selection Sort** algorithm.

### Input
arr = [4,3,2,1]

### Output
[1,2,3,4]

## Approach
- Array full-ah iterate pannum  
- Ovvoru iteration-la, remaining unsorted part-la **minimum element index** kandupudippom  
- Andha minimum element-ah current position-oda **swap** pannum  
- Indha process ellaa elements sort aagura varaikum repeat pannum  

## Code
```java
import java.util.Arrays;

class selectionSort{
    public static void main(String[] args) {
        int[] arr = {4,3,2,1};
        for (int i = 0; i < arr.length; i++) {
            int minIndex = i;
            for(int j =i+1;j<arr.length;j++){
                if(arr[minIndex]>arr[j]){
                    minIndex = j;  
                }
            }
            int temp = arr[i];
            arr[i]=arr[minIndex];
            arr[minIndex]=temp;
        }
        System.out.println(Arrays.toString(arr));
    }    
}
git add