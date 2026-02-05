# Second Largest Element in an Array

## Problem
Given an integer array, find and return the **second largest element** in the array.

### Input
arr = [-1,-2,-3,-4,-5]

### Output
-2

## Approach
- `max` and `secondMax` rendu variables-ah `Integer.MIN_VALUE`-oda initialize pannum  
- Array full-ah iterate pannum  
- Current element `max`-vida perusa irundhaa:
  - `secondMax`-la old `max` store pannum  
  - `max`-ah current element-aa update pannum  
- Illatti, current element `max`-vida chinna but `secondMax`-vida perusa irundhaa:
  - `secondMax`-ah update pannum  

### Edge Cases
- **All elements negative** irundhaalum logic work aagum  
- **Duplicate max values** irundhaa, second largest distinct value dhaan consider pannum  
- Array size `< 2` irundhaa, second largest element exist aagadhu (intha code assume pannudhu minimum 2 elements irukkum nu)

## Code
```java
public class Main {
    public static void main(String[] args) {
        int[] arr = {-1,-2,-3,-4,-5};
        int ans = secondlargestElement(arr);
        System.out.print(ans);
    }

    public static int secondlargestElement(int[] arr){
        int max = Integer.MIN_VALUE;
        int secondMax = Integer.MIN_VALUE;

        for(int i = 0; i < arr.length; i++){
            if(arr[i] > max){
                secondMax = max;
                max = arr[i]; 
            }    
            else if(arr[i] < max && arr[i] > secondMax){
                secondMax = arr[i];
            }
        }
        return secondMax;       
    }
}