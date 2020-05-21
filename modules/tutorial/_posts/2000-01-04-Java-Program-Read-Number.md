---
title: Java Program to read a number
---

# Java Program to read integer value from the Standard Input
<br><br>

In this program we will see how to read an integer number entered by the user. Scanner class is in `java.util package`. It is used for capturing the input of the primitive types like int, double etc. and strings.

We will import the package `java.util.Scanner` to use the Scanner. In order to read the input provided by user, we first create the object of Scanner by passing `System.in` as parameter. Then we are using `nextInt()` method of Scanner class to read the integer. 

```
import java.util.Scanner;

public class Read_Input {

    public static void main(String[] args) {

        /* This reads the input provided by user
         * using keyboard
         */
        Scanner scan = new Scanner(System.in);
        System.out.print("Enter any number: ");

        // This method reads the number provided using keyboard
        int num = scan.nextInt();

        // Closing Scanner after the use
        scan.close();
        
        // Displaying the number 
        System.out.println("The number entered by user: "+num);
    }
}
```
Remember, to run the file, you must save it with the class name `Read_Input.java` and then you can run it on the terminal:

```
java Read_Input`
```

**Output:**

```
Enter any number: 101
The number entered by user: 101
```

<br><br>
### Click Next Button
