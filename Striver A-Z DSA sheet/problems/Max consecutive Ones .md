# Max Consecutive Ones

## Problem
Given a binary array `nums`, return the **maximum number of consecutive 1's** in the array.

(LeetCode Problem No: **485**)

### Input
nums = [1,1,0,1,1,1]

### Output
3

## Approach
- `count` variable current consecutive 1s count panna use pannum  
- `max` variable maximum consecutive 1s store panna use pannum  
- Array full-ah iterate pannum  
- Current element `1` na:
  - `count` increment pannum  
  - `max`-um update pannum  
- Current element `0` na:
  - `count` reset to `0`  
- Loop mudinja apram `max` value return pannum  

## Code
```java
class Solution {
    public int findMaxConsecutiveOnes(int[] arr) {
        int count = 0;
        int max = 0;

        for(int i = 0; i < arr.length; i++){
            if(arr[i] == 1){
                count++;
                max = Math.max(max, count);
            }
            else{
                count = 0;
            }
        }
        return max;
    }
}