# Max Number of K-Sum Pairs (1679)

## Idea
- Two pointers
- Find pairs that equal `k`

## Approach
- Sort array
- left = 0
- right = last index
- Check sum
- Move pointers
- Count pairs

## Complexity
- Time: O(n log n) because sorting takes O(n log n) and the two-pointer scan takes O(n)
- Space Complexity: O(1) because only a constant amount of extra memory is used


class Solution {
    public int maxOperations(int[] nums, int k) {
        int count = 0;
        int  left = 0; // look at first indexes
        int right = nums.length-1; //to reach at last index 

        while(left < right){ // continue while a valid pair can exist
            if(nums[left] + nums[right] == k){ // compare values, not indexes
                count++;
                left++; 
                right--;
            }else if (nums[left]+nums[right]>k){
                left++;
                // count++;
            }else{
                right--;
                // count++;
            }
        }

        return count; 
    }
}

// Time complexity: O(n logn) because you are shorted like a merge sorted 
// Space complexity: O(n) because no data structere use! 

/* 
example:
pointer1 = 0
pointer2 = 4

0 + 4 = 4  ❌ index math

nums[0] + nums[4]
3 + 3 = 6  ✅ value math
*/