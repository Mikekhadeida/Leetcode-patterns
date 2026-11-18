import java.util.*;


public class Main {

    public static ArrayList<Integer> findUnique(int[] nums) {

        HashMap<Integer, Integer> hashmap1 = new HashMap<>(); 
        // Hashmap<Integer, Integer> hashMap2 = new HashMap<>();
        // int number =0; 
       for(int i =0; i<nums.length; i++){
           // hashmap1.put(nums[i]);
           if(!hashmap1.containsKey(nums[i])){
               hashmap1.put(nums[i], 1);
           }else{
               hashmap1.put(nums[i], hashmap1.get(nums[i])+1);
           }
       }

        // need to create an ArrayList to store the numbers
        ArrayList<Integer> result = new ArrayList<>(); 
        
        for(int nums1 : nums){
            if(hashmap1.get(nums1) == 1){
                result.add(nums1);
            }
        }
        return result; 
  
}
    public static void main(String[] args) {
        int[] nums = {4, 2, 4, 3, 2, 5};

        System.out.println(findUnique(nums));
        // Expected output: [3, 5] 
        // because we only want numbers with a count of 1. not 2 
    }
}


## Complexity

**Time Complexity:** O(n)

Time complexity: O(n), because you loop through the array twice.

**Space Complexity:** O(n)

Space complexity: O(n), because the HashMap and ArrayList can store up to n elements.