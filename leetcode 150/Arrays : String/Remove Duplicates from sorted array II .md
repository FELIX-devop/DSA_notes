# Remove Duplicates from Sorted Array II

## Problem
Given a sorted integer array `nums`, remove some duplicates **in-place** such that each unique element appears **at most twice**.  
Return the new length of the array after removing duplicates.

Do not allocate extra space for another array.

(LeetCode Problem No: **80**)

### Input
nums = [1,1,1,2,2,3]

### Output
5

## Approach
- Array sorted irukkum nu guarantee irukku  
- First two elements always allowed (maximum twice occurrence)  
- `left = 2` initialize pannum (write pointer)  
- `right` pointer use panni array traverse pannum  
- Current element `nums[right]` compare pannum with `nums[left - 2]`  
- Equal illa-na:
  - Value valid → `nums[left] = nums[right]`  
  - `left++`  
- Loop mudinja apram `left` dhaan new length  

## Code
```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int size = nums.length;

        // first two elements always allowed
        if(size <= 2) return size;

        int left = 2;

        for(int right = 2; right < size; right++){
            if(nums[right] != nums[left - 2]){
                nums[left] = nums[right];
                left++;
            }
        }
        return left;
    }
}