class Solution {
    public void moveZeroes(int[] nums) {
        int pointer = 0; //starts count from 0 to the rest (Depends how many on array)
        
    
        for(int i = 0; i<nums.length; i++){
            
            if(nums[i]!=0){ //use only with number instead of zero, other wise skip the zero
                int temp = nums[pointer]; // example ,i = 1 → nums[i] = 1 (non-zero)
                nums[pointer] = nums[i];  //nums[0] ↔ nums[1]
                nums[i]=temp;             //nums[1] ↔ nums[0]

                pointer++;  // go to next position
            }
        }
    }
}
