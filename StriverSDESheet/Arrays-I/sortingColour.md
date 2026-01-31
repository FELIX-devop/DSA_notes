# Sort Colors

## Problem
Given an array `nums` with `n` objects colored red, white, or blue, sort them **in-place** so that objects of the same color are adjacent, with the colors in the order **red, white, and blue**.

We use the integers:
- `0` → red  
- `1` → white  
- `2` → blue  

You must solve this problem **without using the library's sort function**.

(LeetCode Problem No: **75**)

### Input
nums = [2,0,2,1,1,0]

### Output
[0,0,1,1,2,2]

## Approach
Idhu **brute force approach**.

- Outer loop use panni, current index element-ah select pannum  
- Inner loop use panni, remaining elements-oda compare pannum  
- If current element perusa irundhaa, smaller element-oda **swap** pannum  
- Indha process full array sort aagura varaikum repeat pannum  

## Code
```java
class Solution {
    public void sortColors(int[] nums) {
        for(int i = 0; i <= nums.length - 1; i++){
            for(int j = i + 1; j < nums.length; j++){
                if(nums[i] > nums[j]){
                    int temp = nums[i];
                    nums[i] = nums[j];
                    nums[j] = temp;
                }
            }
        }
    }
}