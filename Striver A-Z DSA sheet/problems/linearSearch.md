# Linear search

## Problem
search for a element from the given array

## Approach
iterate the entire array and check the element is equal to target

## Code
```java
(
public class Main {
    public static void main(String[] args) {
        int arr []={1,2,3,4,5,6,7,8,};
        int target =8;
        boolean result=true;
        for(int i =0;i<arr.length;i++){
            if(arr[i]==target){
                result=true;
            }
            else result=false;
        }System.out.print(result);
    }
})