
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

        while (request != 5)
        {
            System.out.print("Enter the operation that you would like to proceed with: \n1.Find the average\n2.Find the odd sum\n3.Find smallest\n4.Find largest");
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
                    System.out.println(showSmallest(target));
                    break;  
                case 4:
                    System.out.println(showLargest(target));
                    break;
                case 5:
                    System.out.println("Exiting..."); 
                    break;
                default:
                    System.out.println("You entered an invalid response.");
                    break; 
            } 
        }

    }

    public static int showLargest(int[] array)
    {
        int largest = Integer.MIN_VALUE;
        for(int i: array)
        {
            if(i > largest)
            {
                largest = i;
            }
        }
        return largest;
    }

    public static int showSmallest(int[] array)
    {
        int smallest = Integer.MAX_VALUE;
        for(int i: array)
        {
            if(i < smallest)
            {
                smallest = i;
            }
        }
        return smallest;
    }
    
    public static int[] differencesFromAverage(int[] array){
        int sum = 0;
        int average;
        int[] differences = new int[array.length];
        for (int i = 0; i < array.length; i++){
            sum += array[i];
        }
        average = sum / array.length;
        for (int i = 0; i < array.length; i++){
            differences[i] = array[i] - average;
        }
        return differences;
    }

    public static void printArray(int[] input)
    {
        int size = input.length;
        for (int i = 0; i < size; i++)
        {
            if (i == 0)
            {
                System.out.print("{ " + input[i] + ",");
            }
            else if(i == (size-1) )
            {
                System.out.print( input[i] + " }" );
            }
            else 
            {
                System.out.print( input[i] + "," );
            }
        }
        System.out.println();
    }
}
