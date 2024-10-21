Practical No – 01 
Implementing Substitution and Transposition Ciphers 
Aim : Design and implement algorithms to encrypt and decrypt messages using classical substitution and 
transposition techniques.
A. Caesar Cipher
B. Monoalphabetic Cipher
C. Rail Fence Cipher
D. Simple Columnar Technique
E. Vernam Cipher
Source Cod :
A. CaesarCipher.java
import java.util.Scanner;
class CeaserCipher {
 static String encryptCaeser(String message1, int key1){
 char ch;
 String encryptedMessage = " ";
 for ( int i = 0; i < message1.length();++i){
 ch = message1.charAt(i);
 if ( ch >= 'a' && ch <= 'z'){
 ch = (char) (ch + key1);
 if ( ch > 'z'){
 ch = (char) (ch - 'z' + 'a' - 1);
 }
 encryptedMessage += ch;
 } else if (ch >= 'A' && ch <= 'Z'){
 ch = (char) (ch + key1);
 if ( ch > 'Z'){
 ch = (char) ( ch - 'Z' + 'A' - 1);
 }
encryptedMessage += ch;
 }else {
 encryptedMessage += ch;
 }
 }
 return encryptedMessage;
 }
 static String decryptCaesar(String message1, int key1){
 char ch;
 String decryptedMessage = " ";
 for ( int i = 0; i < message1.length(); ++i){
 ch = message1.charAt(i);
 if ( ch >= 'a' && ch <= 'z'){
 ch = (char) (ch - key1);
 if ( ch < 'a'){
 ch= (char) (ch + 'z' - 'a' + 1);
 }
 decryptedMessage += ch;
 } else if ( ch >= 'A' && ch <= 'Z'){
 ch = (char) (ch - key1);
 if ( ch < 'A'){
 ch = (char) ( ch + 'Z' - 'A' + 1);
 }
 decryptedMessage += ch;
 }
 else {
 decryptedMessage += ch;
 }
 }
 return decryptedMessage;
 }
 public static void main(String[] args) {
 String plainText;
 int key;
 String CipherText;
 Scanner sc = new Scanner(System.in);
 System.out.println("Enter a message to encrypt: ");
 plainText = sc.nextLine();
 System.out.println("Enter key: ");
 key = sc.nextInt();
 CipherText = encryptCaeser(plainText, key);
 System.out.println("Cipher Text= " + CipherText);
 System.out.println("Original Text=" + decryptCaesar(CipherText, key));
 }
}
