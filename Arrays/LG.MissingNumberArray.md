# Missing number

## Problem GFG
You are given an array arr[] of size n - 1 that contains distinct integers in the range from 1 to n (inclusive). This array represents a permutation of the integers from 1 to n with one element missing. Your task is to identify and return the missing element.
Input: arr[] = [8, 2, 4, 5, 3, 7, 1]
Output: 6
Explanation: All the numbers from 1 to 8 are present except 6.

## Approach GFG 
i pointer ah 1 to N varikum iterate pani arr[j] equal ah iruka nu pakanum iruntha ok ilana not equal number ah retrun panna num.


## Problem LC
Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.

Input: nums = [3,0,1]

Output: 2

Explanation:

n = 3 since there are 3 numbers, so all numbers are in the range [0,3]. 2 is the missing number in the range since it does not appear in nums.

## Approach LC
using temporary hash array.oru hash array la 12345 store pani athula arr[] present ana number vanthu hash array 0 to 1 change panitu last ah entha number oda hash value 0 nu iruko athn missing.

## Code BF
```java
(class Solution {
    int missingNum(int arr[]) {
        // Arrays.sort(arr);
        for(int i =1;i<=arr.length+1;i++){// [1] ipdi iruntha next elemnt oda compare tha arr.length + 1
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



##CODE OP
class Solution {
    public int missingNumber(int[] arr ) {
        int size = arr.length;
        int [] hashArray = new int[size + 1];// if the question is 0 to N use this or else 1 to N means use size +2
        for(int i = 0;i<size;i++){
            hashArray[arr[i]]=1;
        }
        for(int i = 0;i<hashArray.length;i++){
            if(hashArray[i]==0){
                return i;
            }
        }
        return -1;
    }
} 









