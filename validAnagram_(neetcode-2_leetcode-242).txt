import java.util.Arrays;
class Solution {
    public boolean isAnagram(String s, String t) {
        if (s.length() != t.length()) {
            return false;
        }
    
    char[] sArray = s.toCharArray();
    char[] tArray = t.toCharArray();
    Arrays.sort(sArray);
    Arrays.sort(tArray);
    return Arrays.equals(sArray, tArray);
}
public static void main(String[] args) {
        Solution sol = new Solution();
        String s1 = "anagram";
        String t1 = "nagaram";
        System.out.println(sol.isAnagram(s1,t1));
        String s2 = "rat";
        String t2 = "car";
        System.out.println(sol.isAnagram(s2,t2));
    }
}
