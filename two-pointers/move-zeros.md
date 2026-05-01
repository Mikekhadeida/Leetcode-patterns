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
- This keeps all non-zero elements in order while pushing zeros to the end

## Time Complexity & Space Compexity 
- Time Complexity: O(n) — we iterate through the array once, processing each element exactly once.
- Space Complexity: O(1) — we use a constant amount of extra space (only a pointer and a temporary variable).

## Code
```java
class Solution {
    public void moveZeroes(int[] nums) {
        int pointer = 0;

        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                int temp = nums[pointer]; //Swap 
                nums[pointer] = nums[i];
                nums[i] = temp;
                pointer++; // move to next position
            }
        }
    }
}