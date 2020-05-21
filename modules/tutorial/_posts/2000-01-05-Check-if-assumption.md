---
title: Java Program to check if Number is Positive or Negative
---

# Java Program to check if Number is Positive or Negative
<br><br>

Now we will write two java programs. The first java program checks whether the specified number is positive or negative. The second program takes the input number (entered by user) and checks whether it is positive or negative and displays the result.

- If a number is greater than zero then it is a positive number
- If a number is less than zero then it is a negative number
- If a number is equal to zero then it is neither negative nor positive.


### Example 1: Program to check whether the given number is positive or negative

In this program we have specified the value of number during declaration and the program checks whether the specified number is positive or negative. 

```
public class Demo
{
    public static void main(String[] args) 
    {
        int number=109;
        if(number > 0)
        {
            System.out.println(number+" is a positive number");
        }
        else if(number < 0)
        {
            System.out.println(number+" is a negative number");
        }
        else
        {
            System.out.println(number+" is neither positive nor negative");
        }
    }
}
```

**Output**
```
109 is a positive number
```
<br><br>

### Example 2: Check whether the input number(entered by user) is positive or negative

Here we are using Scanner to read the number entered by user, like we did in the previous exercise, and then the program checks and displays the result.

```
import java.util.Scanner;
public class Demo
{
    public static void main(String[] args) 
    {
        int number;
        Scanner scan = new Scanner(System.in);
        System.out.print("Enter the number you want to check:");
        number = scan.nextInt();
        scan.close();
        if(number > 0)
        {
            System.out.println(number+" is positive number");
        }
        else if(number < 0)
        {
            System.out.println(number+" is negative number");
        }
        else
        {
            System.out.println(number+" is neither positive nor negative");
        }
    }
}
```

**Output**
```
Enter the number you want to check:-12
-12 is negative number
```

<br><br>
## Click Next Button
