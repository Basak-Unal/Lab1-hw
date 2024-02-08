# Lab1-hw
/**
 * This s the file in which the interactions with the users are managed and executed
 * @author Erez Koc
 */

import java.util.Scanner;
import java.lang.Math;

public class Menu 
{

    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in); 
        System.out.print("Enter the array size:" );
        int size = in.nextInt();
        int[] target = new int[size];
        
        // the following for loop generates random integers to fill the array that is created in accordence with user guidelines.
        for (int i = 0; i < size; i++)
        {
            target[i] =(int)(Math.random() * 100 + 1);
        }

        int request = 0;

        while (request != 4)
        {
            System.out.print("Enter the operation that you would like to proceed with: \n1.Find the average\n2.Find the odd sum\n3.Find\n");
            request = in.nextInt();

           // The following switch case manages the inputs of the user according to the task descriptions.
            switch (request) {
                case 1:
                     System.out.println("1");
                    break;
            
                case 2:
                    System.out.println("2");
                    break;
                case 3:
                    System.out.println("3");
                    break;  
                case 4:
                    System.out.println("Exiting..."); 
                    break;
                default:
                    System.out.println("You entered an invalid response.");
                    break; 
            } 
        }

    }
}
