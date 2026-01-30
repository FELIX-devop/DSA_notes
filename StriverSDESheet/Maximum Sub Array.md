# Maximum Subarray

## Problem
Given an integer array `arr`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

### Input
arr = [-2,1,-3,4,-1,2,1,-5,4]

### Output
6

## Approach
Idhu **brute force approach**.

- Outer loop use panni, subarray start index-ah select pannum  
- Inner loop use panni, andha start index-la irundhu end varaikum sum calculate pannum  
- Ovvoru step-la current sum-um `max` value-um compare panni maximum-ah update pannum  
- Ella possible subarrays check pannitu final maximum sum return pannum  

## optimal solution
 Kadane's algo

 ## Notes
![Kadane's algo steps](source/kadane's algorithm.png)


## Code
```java
class Solution {
    public int maxSubArray(int[] arr) {
        
        int max = Integer.MIN_VALUE;
        for(int i = 0; i < arr.length; i++){
            int sum = 0;
            for(int j = i; j < arr.length; j++){
                sum += arr[j];
                max = Math.max(sum, max);
            }
        }
        return max;
    }
}
```
## kadane's algo code
```java
class Solution {
    public int maxSubArray(int[] arr) {
        int max = Integer.MIN_VALUE;
        int sum = 0;
        for(int i = 0;i<arr.length;i++){
            sum += arr[i];
            max = Math.max(sum,max);
            if(sum < 0){
                sum = 0;
            }
        }
        return max;
    }
}
