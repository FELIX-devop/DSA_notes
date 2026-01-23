# Check if array is sorted

## Problem
Given an array arr[], check whether it is sorted in non-decreasing order. Return true if it is sorted otherwise false.

## Approach
Input: arr[] = [10, 20, 30, 40, 50]
Output: true
Explanation: The given array is sorted.


## Code
```java
(class Solution {
    public boolean isSorted(int[] arr) {
        boolean ans = false;
        if(arr.length == 0)return false;
        if(arr.length == 1)return true;
            
        
       
        int i = 0;
        for(int j = 1;j<arr.length;j++){
            
            if(arr[i]<=arr[j]){
                ans = true;
                i++;
            }
            else{
                ans = false;
                break;
            }
            
        }return ans;
    }
})


