# Single Number

## Problem
Given a non-empty array of integers `nums`, every element appears **twice** except for **one** element.  
Find and return that single element.

(LeetCode Problem No: **136**)

### Input
nums = [2,2,1]

### Output
1

## Approach
Idhu **brute force approach**.

- Outer loop use panni, ovvoru element-ah pick pannum  
- Inner loop use panni, same element vera index-la irukka nu check pannum  
- Same value kidaichaa `flag` set pannum  
- End-la `flag` set aagala-na, andha element dhaan **single number**, adhai return pannum  

## Approach
Idhu **better solution using hasharray**.

⚠️ **Note:**  
- Indha approach **`nums[i] >= 0`** irundhaa mattum dhaan work aagum  

- First array length `1` na, direct-ah andha element return pannum  
- Array-la irukkura **maximum value** kandupudippom  
- `max + 1` size-oda oru hash array create pannum  
- `nums` array traverse panni, ovvoru number-oda frequency hash array-la store pannum  
- Next, marubadiyum `nums` traverse panni:
  - Yaaroda frequency `1` irukko, adhai return pannum  



## Code BF
```java
class Solution {
    public int singleNumber(int[] nums) {
        int count = 0;

        for(int i = 0; i < nums.length; i++){
            int flag = 0;
            for(int j = 0; j < nums.length; j++){
                if(i != j && nums[i] == nums[j]){
                    flag = 1;
                }
            }
            if(flag == 0) return nums[i];
        }
        return -1;
    }
}
```
## code BT

```java
class Solution {
    public int singleNumber(int[] nums) {
        // only the arayy from 0 to N becoz it is hashArray so no negatives
        if(nums.length == 1) return nums[0];

        int max = nums[0];
        for(int i = 1; i < nums.length; i++){
            if(nums[i] > max){
                max = nums[i];
            }
        }

        int[] hashArray = new int[max + 1];
        for(int num : nums){
            hashArray[num]++;
        }

        for(int num : nums){
            if(hashArray[num] == 1){
                return num;
            }
        }

        return -1;
    }
}
```
# code OP
```java 
class Solution {
    public int singleNumber(int[] nums) {
        int ans = 0;
        for(int num : nums){
            ans ^= num;
        }
        return ans;
    }
}