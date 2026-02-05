# Remove Duplicates from an array

## Problem GFG
Given an array arr[] consisting of positive integers, return the array by removing all duplicate numbers.

Example:

Input: arr[] = [2, 2, 3, 3, 7, 5] 
Output: [2, 3, 7, 5]
Explanation: After removing the duplicates 2 and 3 we get 2 3 7 5.

## Problem LC
26.Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same.

Consider the number of unique elements in nums to be k​​​​​​​​​​​​​​. After removing duplicates, return the number of unique elements k.

The first k elements of nums should contain the unique numbers in sorted order. The remaining elements beyond index k - 1 can be ignored.

Example 1:

Input: nums = [1,1,2]
Output: 2, nums = [1,2,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).


## Approach GFG
using treeset to ingore duplicate and maintain sorted order.and add it to the List.

## Approach LC
using two pointer and compare the i and j.and move to correct place and return the array size as i value + 1;

## Approach OP
same as the abouve appraoch LC but code patha changes therium using two pointer and compare the i and j.and move to correct place and return the array size as i value + 1;

## Code GFG
```java
(class Solution {
    ArrayList<Integer> remDuplicate(int arr[]) {
        TreeSet<Integer> set = new TreeSet<>();
        ArrayList<Integer> list = new ArrayList<>();
        for(int i = 0;i<arr.length;i++){
            set.add(arr[i]);
        }
        for(int nums:set){
            list.add(nums);
        }
        return list;
    }
})
```

## Code LC
```java 
class Solution {
    public int removeDuplicates(int[] arr) {
        int size = arr.length;
        int i =0;
        int j=i+1;
        while(j!=size){
            if(arr[i]==arr[j]){
                j++;
            }
            else{
                arr[i+1]=arr[j];
                i++;
            }
        }
         return i+1;   
        }
    }
  ```
  ## code optimal
  ```java
  class Solution {
    public int removeDuplicates(int[] arr) {
        int left =0;
        for(int right =1;right<arr.length;right++){
            if(arr[left]!=arr[right]){
                left++;
                arr[left] = arr[right];
            }
        }
        return left + 1;
    }
}







