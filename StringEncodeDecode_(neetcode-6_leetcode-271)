import java.util.ArrayList;
import java.util.List;

public class Codec {
    public String encode(List<String> strs) {
        StringBuilder encoded = new StringBuilder();
        for (String str : strs) {
            encoded.append(str.length()).append("#").append(str);
        }
        return encoded.toString();
    }

    public List<String> decode(String s) {
        List<String> decoded = new ArrayList<>();
        int i = 0;
        
        while (i < s.length()) {
            int delimiterIndex = s.indexOf('#', i);
            
            int length = Integer.parseInt(s.substring(i, delimiterIndex));
            
            String str = s.substring(delimiterIndex + 1, delimiterIndex + 1 + length);
            decoded.add(str);
            
            i = delimiterIndex + 1 + length;
        }
        
        return decoded;
    }

    public static void main(String[] args) {
        Codec codec = new Codec();

        List<String> strs1 = List.of("neet", "code", "love", "you");
        String encoded1 = codec.encode(strs1);
        System.out.println("Encoded: " + encoded1);
        List<String> decoded1 = codec.decode(encoded1);
        System.out.println("Decoded: " + decoded1);

        List<String> strs2 = List.of("we", "say", ":", "yes");
        String encoded2 = codec.encode(strs2);
        System.out.println("Encoded: " + encoded2);
        List<String> decoded2 = codec.decode(encoded2);
        System.out.println("Decoded: " + decoded2);
    }
}
