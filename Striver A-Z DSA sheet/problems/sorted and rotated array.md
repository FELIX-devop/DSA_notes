# Check if Array is Sorted and Rotated

## Problem
Given an integer array `nums`, return `true` if the array is **sorted and rotated**, otherwise return `false`.

An array is considered sorted and rotated if it was originally sorted in non-decreasing order and then rotated some number of times.

(LeetCode Problem No: **1752**)

### Input
nums = [3,4,5,1,2]

### Output
true

## Approach
- `count` variable use panni **decreasing order occurrences** count pannum  
- Array full-ah iterate pannum  
- Current element `nums[i]` next element-vida perusa irundhaa (`nums[(i+1) % nums.length]`):
  - `count` increment pannum  
- Circular check (`% nums.length`) use pannradhu:
  - Last element-um first element-um compare panna  
- Sorted & rotated array-la **maximum one time mattum** decreasing order irukkanum  
- `count <= 1` irundhaa `true`, illatti `false`

## Notes
![sortedAndRotatedArray](../source/sorted%20and%20rotated%20array.png)


## Code
```java
class Solution {
    public boolean check(int[] nums) {
        int count = 0;
        
        for(int i = 0; i < nums.length; i++){
            // circular check for last and first element
            if(nums[i] > nums[(i + 1) % nums.length]){
                count++;
            }
        }
        // only one decreasing point allowed
        return count <= 1;
    }
}