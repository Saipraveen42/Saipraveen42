import java.security.SecureRandom;
import java.util.Random;

public class CaptureCodeGenerator {
    
    private static final String CHARACTERS = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
    private static final int CODE_LENGTH = 6; // Adjust the length of the capture code as needed
    
    private static SecureRandom random = new SecureRandom();

    public static void main(String[] args) {
        String captureCode = generateCaptureCode();
        System.out.println("Generated Capture Code: " + captureCode);
    }

    public static String generateCaptureCode() {
        StringBuilder sb = new StringBuilder(CODE_LENGTH);
        for (int i = 0; i < CODE_LENGTH; i++) {
            sb.append(CHARACTERS.charAt(random.nextInt(CHARACTERS.length())));
        }
        return sb.toString();
    }
}
