# GFG.UnionOfTwoSortedArrays

## Problem
Given two sorted arrays a[] and b[], where each array may contain duplicate elements , the task is to return the elements in the union of the two arrays in sorted order.
Union of two arrays can be defined as the set containing distinct common elements that are present in either of the arrays.

Input: a[] = [1, 2, 3, 4, 5], b[] = [1, 2, 3, 6, 7]
Output: [1, 2, 3, 4, 5, 6, 7]
Explanation: Distinct elements including both the arrays are: 1 2 3 4 5 6 7.


## Approach 1
TreeSet use pani unique elements lam sorted order la set la potutu final addALL use pani arraylist la potachu.
## Approach 2
a and b array ula elements check pani ethu smaller atha list la add pnaite varanum existing elements add panna koodathu oncce either one array end agituna remaining array la ula ella elemst iterate pannaum.

## Code
```java
(class Solution {
    public static ArrayList<Integer> findUnion(int a[], int b[]) {
        ArrayList<Integer> list = new ArrayList<>();
        TreeSet<Integer> set = new TreeSet<>();
        for(int i =0;i<a.length;i++){
            set.add(a[i]);
        }
        for(int i =0;i<b.length;i++){
            set.add(b[i]);
        }
        
        list.addAll(set);
        return list;
    }
}
)


## another aproach 
class Solution {
    public static ArrayList<Integer> findUnion(int a[], int b[]) {
        ArrayList<Integer> list = new ArrayList<>();
        int size1 = a.length;
        int size2 = b.length;
        int i = 0;
        int j = 0;                                              
        while(i < size1 && j < size2){
            if(a[i]<=b[j]){
                if(!list.contains(a[i])){
                    list.add(a[i]);
                }i++;
           }
           else{
               
                if(!list.contains(b[j])){
                    list.add(b[j]);
                }j++;
               
                }
        }
        while(i<size1){
            if(!list.contains(a[i])){
                    list.add(a[i]);
                }i++;
        }
        while(j<size2){
            if(!list.contains(b[j])){
                    list.add(b[j]);
                }j++;
        }
        return list;
    }
}

