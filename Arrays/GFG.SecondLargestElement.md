# Second Largest

## Problem
Given an array of positive integers arr[], return the second largest element from the array. If the second largest element doesn't exist then return -1.

Note: The second largest element should not be equal to the largest element.

Input: arr[] = [12, 35, 1, 10, 34, 1]
Output: 34
Explanation: The largest element of the array is 35 and the second largest element is 34.

## Approach BF
Array sort pannanum so largest elemnet last la irukum now loop ah last leruthu reverse la run panitu condition vachi second largest element edukanum.

## Code
```java
(class Solution {
    public int getSecondLargest(int[] arr) {
        int ans =-1;
        Arrays.sort(arr);
        int i = arr.length-1;
        while(i>0){
            
            if(arr[i]>arr[i-1]){
                ans = arr[i-1];
                break;
            }
            else i--;
        }
        return ans;   
    }
})









