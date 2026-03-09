# Ex.No:5(C)  FILE HANDLING USING JAVA
## QUESTION:
Write a program to count the number of characters in a file.

## AIM:
To count and display the total number of characters in a file using FileReader.

## ALGORITHM :
1.	Ask the user for the file name.
2.	Open the file using FileReader.
3.	Read each character one by one until the end of the file.
4.	Increment a counter for each character read.
5.	Display the total character count.

## PROGRAM:
 ```
/*
Program to implement a File Handling using Java
Developed by: MANJUSRI KAVYA R
Register Number: 212224040186
*/
```

## SOURCE CODE:
```java
import java.io.*;

public class FileCharacterCount {
    public static void main(String[] args) {
        try {
            // Use BufferedReader to read input
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

            // Read the text to write (assume file name is fixed)
            String text = br.readLine();

            // Use a fixed file name
            String fileName = "output.txt";

            // Write text to file
            try (FileWriter fw = new FileWriter(fileName)) {
                if (text != null) {
                    fw.write(text);
                }
            }

            // Count characters in file
            int charCount = 0;
            try (FileReader fr = new FileReader(fileName)) {
                while (fr.read() != -1) {
                    charCount++;
                }
            }

            System.out.println("Number of characters written to the file: " + charCount);

        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}

```

## OUTPUT:
<img width="1271" height="303" alt="image" src="https://github.com/user-attachments/assets/8417184e-b934-4c43-a19c-4bc7cec02f4e" />



## RESULT:
The program successfully reads the file and prints the total number of characters present in it.




