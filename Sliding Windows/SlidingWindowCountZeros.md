class Solution {
    public int countZeros(int[] nums, int k) {
        int count = 0;

        // Count zeros in the first window
        for (int i = 0; i < k; i++) {
            if (nums[i] == 0) {
                count++;
            }
        }

        // Slide through the rest of the array
        for (int i = k; i < nums.length; i++) {

            // If a 0 enters the window
            if (nums[i] == 0) {
                count++;
            }

            // If a 0 leaves the window
            if (nums[i - k] == 0) {
                count--;
            }
        }

        return count;
    }
}