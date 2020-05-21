---
title:Java Program to calculate simple interest
---

# Java Program to Calculate Simple Interest
<br><br>

In this task, we will write a java program to calculate simple interest.

#### Simple Interest Formula

```
Simple Interest = (P × R × T)/100
```
Where:

- P is Principal amount.
- R is rate per annum.
- T is time in years.

For example: Let’s say you deposit 2000 pounds in a bank account at a interest rate of 6% per annum for 3 years, calculate the simple interest at the end of 3 years.

### Writing the program

In the following example we are taking the values of p, r and t from user and then we are calculating the simple interest based on entered values.

Remember, al you have to do is copy this code into the editor and then run it on the terminal as `java Simple_Interest` + Enter key.

```
import java.util.Scanner;
public class Simple_Interest
{
    public static void main(String args[]) 
    {
        float p, r, t, sinterest;/*declaring four float variables at once*/
        Scanner scan = new Scanner(System.in);
        System.out.print("Enter the principal : ");
        p = scan.nextFloat();
        System.out.print("Enter the rate of interest in percentage: ");
        r = scan.nextFloat();
        System.out.print("Enter the time period in years: ");
        t = scan.nextFloat();
        scan.close();
        sinterest = (p * r * t) / 100;/*executing the simple interest formula using simple operators*/
        System.out.print("Simple Interest is: £" +sinterest+" over a period of "+t+" years."); //print the result
    }
}
```
**Output**

```
Enter the Principal : 2000
Enter the Rate of interest in percentage: 6
Enter the Time period in years: 3
Simple Interest is: £360.0 over a period of 3.0 years.
```

<br><br>


