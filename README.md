import java.util.Scanner;

public class reverseString {
    public static void main(String args[]){
    Scanner sc = new Scanner(System.in);

    //input
        System.out.print("Enter the value of string: ");
        String str = sc.nextLine().trim();

        //use StringBuilder to store the reversed sentence
        StringBuilder reversedSentence = new StringBuilder();
        int end = str.length();

    //reverse the order of words
       for(int i = str.length() - 1; i >= 0; i--) {
           if(str.charAt(i) == ' ') {
               //Skip multiple spaces
               end = i;
           } else if (i == 0 || str.charAt(i - 1)==' ' ) { // Detect the Start of a Word
               //Found the start of a word
               if (reversedSentence.length() > 0) { // Handle Spaces Between Words
                   reversedSentence.append(" "); //Append the Word
               }

               reversedSentence.append(str.substring(i, end));
           }
       }
        System.out.println("Reversed sentence : " + reversedSentence.toString().trim());
        sc.close();

    }
}
