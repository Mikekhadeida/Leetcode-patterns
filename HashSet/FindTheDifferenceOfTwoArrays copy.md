import java.util.*;

class Solution {
    public List<List<Integer>> findDifference(int[] nums1, int[] nums2) {

        HashSet<Integer> hashSet1 = new HashSet<>();
        HashSet<Integer> hashSet2 = new HashSet<>();

        // Store unique numbers from nums1 and nums2
        for(int i = 0; i < nums1.length; i++){
            hashSet1.add(nums1[i]);
        }

        for(int i = 0; i < nums2.length; i++){
            hashSet2.add(nums2[i]);
        }

        // Store the final differences
        ArrayList<Integer> result1 = new ArrayList<>();
        ArrayList<Integer> result2 = new ArrayList<>();

        // Find numbers in nums1 that are not in nums2
        for(int number1 : hashSet1){
            if(!hashSet2.contains(number1)){
                result1.add(number1);
            }
        }

        // Find numbers in nums2 that are not in nums1
        for(int number2 : hashSet2){
            if(!hashSet1.contains(number2)){
                result2.add(number2);
            }
        }

        // Return both result lists
        return Arrays.asList(result1, result2);
    }
}

/*
Time Complexity: O(n + m)
- n = length of nums1
- m = length of nums2
- We loop through both arrays to add numbers to the HashSets.
- We loop through both HashSets to find the differences.
- HashSet add() and contains() take O(1) time on average.
- Total time: O(n + m).

Space Complexity: O(n + m)
- hashSet1 stores up to n unique numbers from nums1.
- hashSet2 stores up to m unique numbers from nums2.
- result1 and result2 store the differences.
- Total extra space: O(n + m).
*/