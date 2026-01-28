# Palindrome Number

## Problem
Given an integer `x`, return `true` if `x` is a palindrome, and `false` otherwise.

(LeetCode Problem No: **9**)

### Input
x = 121

### Output
true

## Approach
- Negative numbers palindrome illa, so first `false` return pannum  
- Original number store pannum  
- Number-ah reverse pannum using modulo and division  
- Original number-um reversed number-um equal-na `true`, illatti `false`

## Code
```java
class Solution {
    public boolean isPalindrome(int x) {

        // negative numbers palindrome illa
        if(x < 0) return false;

        int original = x;
        int reverse = 0;

        while(x > 0){
            int digit = x % 10;
            reverse = reverse * 10 + digit;
            x = x / 10;
        }

        return original == reverse;
    }
}