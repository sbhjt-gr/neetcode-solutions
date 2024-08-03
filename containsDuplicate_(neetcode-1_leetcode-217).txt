import java.util.HashSet;
class Solution {
    public boolean containsDuplicate(int[] nums) {
        HashSet<Integer> seen = new HashSet<>();
        for (int num : nums) {
            if (seen.contains(num)) {
                return true;
            }
            seen.add(num);
        }
        return false;
    }
    public static void main(String[] args) {
        Solution solution = new Solution();
        int[] nums1 = {1,2,3,1};
        System.out.println(solution.containsDuplicate(nums1));
        int[] nums2 = {1,2,3,4};
        System.out.println(solution.containsDuplicate(nums2));
        int[] nums3 = {1,1,1,3,3,4,3,2,4,2};
        System.out.println(solution.containsDuplicate(nums3));
    }
}
