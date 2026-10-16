import java.util.*;

class Solution {
    public List<Integer> findCommon(int[] nums1, int[] nums2) {

        HashSet<Integer> set1 = new HashSet<>();
        HashSet<Integer> set2 = new HashSet<>();

        for (int i = 0; i < nums1.length; i++) {
            set1.add(nums1[i]);
        }

        for (int i = 0; i < nums2.length; i++) {
            set2.add(nums2[i]);
        }

        LinkedList<Integer> result = new LinkedList<>();

        for (int number : set1) {
            if (set2.contains(number)) {
                result.add(number);
            }
        }

        return result;
    }
}

## Complexity

**Time Complexity:** O(n + m)

The algorithm loops through both input arrays. HashSet `add()` and `contains()` operations take O(1) average time, so processing all elements takes O(n + m).

**Space Complexity:** O(n + m)

Two HashSets are used to store values from both arrays, and a LinkedList stores the common elements. The amount of extra memory grows with the input size.
