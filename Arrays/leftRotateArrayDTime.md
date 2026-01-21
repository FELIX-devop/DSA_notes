# Left Rotate Array D Times

## Problem
Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

## Approach
reversing by part by part.

## Code
```java
(class Solution {
    public void rotate(int[] arr, int rotateValue) {
        int size = arr.length;
        int d = rotateValue % size;
        int temp[] = new int[d];
        int tempSize=temp.length;
         for(int i=0;i<d;i++){
            temp[i]=arr[i];
        } 
          
        for(int i=d;i<size;i++){
           arr[i-d]=arr[i];
        } 
        int currentIndex=size-tempSize;
        for(int i =0;i < tempSize;i++){
            arr[currentIndex]=temp[i];
            currentIndex++;
        }
        //  int j=0;
        // for(int i=size-d;i<size;i++){
        //     arr[i]=temp[j];
        //     j++;
        // }
        
    }
})