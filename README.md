package GUI;

//Only the scanner utility is used in this class. The SQL imports are not used in this class, although they are used within the referenced "game" class.

import java.io.*;

import java.sql.Connection;

import java.sql.DriverManager;

import java.sql.PreparedStatement;

import java.util.Scanner;





//This is where the name of the class "store" is defined.

public class store

{


        //This is where the main method within the "store" class is defined.


	public static void main(String args[]) throws Exception

	{


            //"option1" is a being defined as a new instance of the game class here, that can now be referenced and used within it.

		
            game option1 = new game(); 


            //The scanner is being defined here with the name of "input", and it can now be used to collect user inputs and store them within variables.

                             		
	    Scanner input = new Scanner(System.in);


            //These print functions are simply displaying the options available to the user, and have nothing to do with the actual option chosen.
            //The variable called "userinput" is then collecting the number the user chooses to select, which is then used later within the main method.

		
		System.out.println("I N V E N T O R Y    M A N A G E M E N T    S Y S T E M");

		System.out.println("-----------------------------------------------");

		System.out.println("1. ADD NEW ITEM");

		System.out.println("2. UPDATE QUANTITY OF EXISTING ITEM");

		System.out.println("3. REMOVE ITEM");

		System.out.println("4. VIEW DAILY TRANSACTION REPORT");

		System.out.println("---------------------------------");

		System.out.println("5. Exit");
		
		
		System.out.printf("Enter a choice and Press ENTER to continue[1-5]: %n%n");

		int userinput = input.nextInt();
			

		

              //This "while" is allowing a set of exterior classes to be entered, as long as the argument defined by the while function is false. If the argument becomes false, then the program is exited by default.

              //The exterior classess are accessed by referencing the seperate instance of the relevant class, followed by the relevant method needed pertaining to the function stated by each option.

              //If the "while" argument becomes true, then the loop is excited, as well as the program. This leads to a final print statement that informs the user that they have exited the program.



                        while(userinput !=5)
		{
			if (userinput>5 || userinput<1) {

				System.out.println("This doesn't appear to be a valid option...!");

				break;

			}

			if (userinput == 1)	{

			option1.getConnection();

			option1.createTable();

			option1.addGame();
		
				break;
			}

			else if (userinput == 2) {
		
				System.out.print("\n Item quantity updated");

				break;

			}

			else if (userinput == 3) {

				System.out.print("\n Item Removed");

				break;

			}
	
			else if (userinput == 4) {

				System.out.print("\n Report printed");	

				break;

			}	
			
		}
		
	System.out.println("\n\n Thanks for using this program...!");

	}

}
