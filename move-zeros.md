# Move Zeroes (283)

## Problem
Given an integer array, move all zeros to the end while maintaining the relative order of non-zero elements.

## Idea
Use a pointer to track where the next non-zero element should go.

## Approach
- Initialize a pointer at index 0
- Iterate through the array
- If the current element is not zero, swap it with the pointer position
- Move the pointer forward after placing a non-zero

## Code
```java
class Solution {
    public void moveZeroes(int[] nums) {
        int pointer = 0;

        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                int temp = nums[pointer];
                nums[pointer] = nums[i];
                nums[i] = temp;
                pointer++;
            }
        }
    }
}