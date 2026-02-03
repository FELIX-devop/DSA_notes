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

Idhu **brute force approach using dutch national flag Algo**.
## Notes
![Dutch National FLag Algorithm](../source/DutchNationalFLagAlgorithm.png)

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
```
## code BT
```java
class Solution {
    public void sortColors(int[] nums) {
        int count0=0;
        int count1=0;
        int count2=0;
        for(int i =0;i<nums.length;i++){
            if(nums[i]==0) count0++;
            else if(nums[i]==1) count1++;
            else count2++;
        }
        for(int i =0;i<count0;i++){
            nums[i] = 0;
        }
        for(int i =count0;i<count0+count1;i++){
            nums[i] = 1;
        }
        for(int i =count0+count1;i<nums.length;i++){
            nums[i] = 2;
        }
    }
}
```
## code OP
### using dutch national flag algo
```java
class Solution {
    public void sortColors(int[] nums) {
    int low = 0;
    int mid = 0;
    int high = nums.length-1;
    int temp = 0;
    while(mid<=high){
        if(nums[mid]==0){
            temp = nums[low];
            nums[low] = nums[mid];
            nums[mid] = temp;
            low++;
            mid++;
        }
        else if(nums[mid]==2){
            temp = nums[mid];
            nums[mid] = nums[high];
            nums[high] = temp;
            high--;
        }
        else mid++;
       
    }         
        
    }
}
