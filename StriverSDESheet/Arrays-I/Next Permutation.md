# Next Permutation

## Problem
Given an array of integers `nums`, find the next permutation of the array.  
If no next permutation is possible, rearrange it as the lowest possible order (ascending).

### Input
nums = [1,2,3]

### Output
[1,3,2]

## Approach
- First **break point** kandupudikanum (right side-la irundhu, `nums[i] < nums[i+1]` irukkura first index).  
- Apram array-ah **reverse direction-la iterate** panni, break point value-vida **first greater number** kandupudikanum.  
- Andha two elements-ah **swap** pannum.  
- Last-ah, **break point-ku apram irukkura ella numbers-um reverse** pannum.

## Notes
![Next Permutation Steps](StriverSDESheet/source/nextpermutation.png)

## Code OP
```java
class Solution {
    public void nextPermutation(int[] nums) {
        int breakpoint = -1;
        int index = -1;
        int size = nums.length;
        
        for(int i =size-2;i>=0;i--){
            if(nums[i]<nums[i+1]){
                breakpoint = i;
                index = i;
                break;
            }
        }
        for(int i =size-1;i>=0;i--){
            if(breakpoint != -1 && nums[i]>nums[breakpoint]){
                int temp = nums[i];
                nums[i] = nums[breakpoint];
                nums[breakpoint] = temp;
                break;
            }
        }
        
        if(breakpoint != -1 ){
            reverse(nums,index+1,size-1);
        }
        else{
            reverse(nums,0,size-1);
        }
        
        
      
    }

      public static void reverse(int[] arr,int start,int end){
            while(start<end){
                int temp = arr[start];
                arr[start] = arr[end];
                arr[end] = temp;
                start++;
                end--;
            }
        }
}
```

