
# GFG.Intersection of Two sorted arrays

## Problem
Given two sorted arrays arr1[] and arr2[]. Your task is to return the intersection of both arrays.
Intersection of two arrays is said to be elements that are common in both arrays. The intersection should not count duplicate elements.
Note: If there is no intersection then return an empty array.

Input: arr1[] = [1, 2, 2, 3, 4], arr2[] = [2, 2, 4, 6, 7, 8]
Output: [2, 4]
Explanation: 2 and 4 are the only common elements.


## Approach BF
a and b rendu array.b array oda same size la visiting array create pannaum like duplicate varama irka athula once visit panita from 0 to 1 ah flag pannanum.
if(list.size()==0 || arr1[i]!=list.get(list.size()-1)) intha check last ah array la duplicate join aga koodathu example {1,2,3,} list la next 3 add aga koodathu so list.size-1 pani last element kadachirum so last elemt is 3 and current element is 3 so list add panna koodathu.



## Code
```java
(public class Main {
    public static void main(String[] args) {
        int[] arr1 = {1, 2, 2, 2, 3, 4, 5, 5, 6};
        int[] arr2 = {2, 2, 3, 3, 5, 5, 7};

        
        ArrayList<Integer> result =intersection(arr1, arr2);

        System.out.println(result);
    }
    
    
    
    public static ArrayList<Integer> intersection(int arr1[], int arr2[]) {
        int n = arr1.length;
        int m = arr2.length;
        ArrayList<Integer> list = new ArrayList<>();
        int [] visitedArray = new int [m];
        for(int i = 0;i<n;i++){
            
            for(int j =0;j<m;j++){
                if(arr1[i]==arr2[j] && visitedArray[j]==0){
                    if(list.size()==0 || arr1[i]!=list.get(list.size()-1)){
                        list.add(arr1[i]);
                        visitedArray[j]=1;
                    }    break;
                }
                if(arr1[i]<arr2[j]) break;
            }
        }
        return list;        
    }


})











