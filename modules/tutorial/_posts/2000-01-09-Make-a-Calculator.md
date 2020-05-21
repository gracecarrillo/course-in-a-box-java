---
title: Java Program to Make a Calculator using Switch Case
---

# Java Program to Make a Calculator using Switch Case
<br><br>

In this Program we are making a simple calculator that performs addition, subtraction, multiplication and division based on the user input. The program takes the value of both the numbers (entered by user) and then user is asked to enter the operation (+, -, * and /), based on the input program performs the selected operation on the entered numbers using switch case. 

The switch case statement is used when we have number of options (or choices) and we may need to perform a different task for each choice.

Here's the code you must run:

```
import java.util.Scanner;

public class Calculator {

    public static void main(String[] args) {

    	double num1, num2;
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter first number:");

        /* We are using data type double so that user
         * can enter integer as well as floating point
         * value
         */
        num1 = scanner.nextDouble();
        System.out.print("Enter second number:");
        num2 = scanner.nextDouble();

        System.out.print("Enter an operator (+, -, *, /): ");
        char operator = scanner.next().charAt(0);

        scanner.close();
        double output;

        switch(operator)/*we are providing a variable in the switch parenthesis*/
        {
            case '+':
            	output = num1 + num2;
                break;

            case '-':
            	output = num1 - num2;
                break;

            case '*':
            	output = num1 * num2;
                break;

            case '/':
            	output = num1 / num2;
                break;

            /* If user enters any other operator or char apart from
             * +, -, * and /, then display an error message to user
             * 
             */
            default:
                System.out.printf("You have entered wrong operator");
                return;//exception handling
        }

        System.out.println(num1+" "+operator+" "+num2+" = "+output);
    }
}
```

**Output**

```
Enter first number:5
Enter second number:5
Enter an operator (+, -, *, /): /
5.0 / 5.0 = 1.0
```
Try different numbers and operators to see how it works!

### Awesome. You've now learned a bit of Java by example. You can find all the exercises we did online here: https://Java-Crash-Course.gracecarrilloc.repl.run


