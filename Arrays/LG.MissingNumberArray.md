# Missing number

## Problem GFG
You are given an array arr[] of size n - 1 that contains distinct integers in the range from 1 to n (inclusive). This array represents a permutation of the integers from 1 to n with one element missing. Your task is to identify and return the missing element.

## Approach GFG 
i pointer ah 1 to N varikum iterate pani arr[j] equal ah iruka nu pakanum iruntha ok ilana not equal number ah retrun panna num.
Input: arr[] = [8, 2, 4, 5, 3, 7, 1]
Output: 6
Explanation: All the numbers from 1 to 8 are present except 6.
## Code
```java
(class Solution {
    int missingNum(int arr[]) {
        // Arrays.sort(arr);
        for(int i =1;i<=arr.length+1;i++){
            int flag =0;
            for(int j = 0;j<arr.length;j++){
                if(arr[j]==i){
                    flag =1;
                    break;
                }
            }if(flag == 0) return i;
        }return -1;
    }
})





