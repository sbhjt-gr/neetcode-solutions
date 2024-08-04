class Solution {
    public int[] topKFrequent(int[] nums, int k) {
        Map<Integer, Integer> frequencyMap = new HashMap<>();
        for (int num : nums) {
            frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);
        }
        List<Integer>[] buckets = new List[nums.length + 1];
        for (int i = 0; i <= nums.length; i++) {
            buckets[i] = new ArrayList<>();
        }
        for (Map.Entry<Integer, Integer> entry : frequencyMap.entrySet()) {
            int frequency = entry.getValue();
            int num = entry.getKey();
            buckets[frequency].add(num);
        }
        List<Integer> result = new ArrayList<>();
        for (int i = buckets.length - 1; i >= 0 && result.size() < k; i--) {
            if (!buckets[i].isEmpty()) {
                result.addAll(buckets[i]);
            }
        }
        int[] resultArray = new int[k];
        for (int i = 0; i < k; i++) {
            resultArray[i] = result.get(i);
        }

        return resultArray;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        int[] nums1 = {1, 1, 1, 2, 2, 3};
        int k1 = 2;
        System.out.println(Arrays.toString(solution.topKFrequent(nums1, k1)));
        int[] nums2 = {1};
        int k2 = 1;
        System.out.println(Arrays.toString(solution.topKFrequent(nums2, k2)));
    }
}
