# Merge Sorted Array

## Problem
You are given two sorted integer arrays `nums1` and `nums2`, and two integers `m` and `n` representing the number of valid elements in `nums1` and `nums2`.

Merge `nums2` into `nums1` as one sorted array.  
The final sorted array should be stored inside `nums1`.

(LeetCode Problem No: **88**)

### Input
nums1 = [1,2,3,0,0,0], m = 3  
nums2 = [2,5,6], n = 3

### Output
[1,2,2,3,5,6]

## Approach
Idhu **brute force approach**.

- First `nums2` elements ellam `nums1` array-oda remaining space-la copy pannum  
- Apram full `nums1` array-ah sort pannum using library sort  
- Result → merged sorted array  

Idhu **op approach**.
1️⃣ nums1 & nums2 last valid elements compare pannrom
2️⃣ Periya (largest) number nums1 last position-la podrom
3️⃣ Andha pointer-ah move pannrom
4️⃣ nums2 finish aagum varai repeat

⸻


## Code bf
```java
import java.util.Arrays;

class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        for(int j = 0, i = m; j < n; j++){
            nums1[i] = nums2[j];
            i++;
        }
        Arrays.sort(nums1);
    }
}
```

# code op
```java
class Solution {
  public void merge(int[] nums1, int m, int[] nums2, int n) {
    int i = m - 1;     
    int j = n - 1;
    int k = m + n - 1; 

    while (j >= 0)
      if (i >= 0 && nums1[i] > nums2[j])
        nums1[k--] = nums1[i--];
      else
        nums1[k--] = nums2[j--];
  }
}
