# DataVisualizer
import java.util.Scanner;
import java.util.regex.Matcher;
import java.util.regex.Pattern;
import java.util.ArrayList;

public class DataVisualizer {
	public static void main(String[] args) {
	  String titleName;
	  String columnOne;
	  String columnTwo;
	  String dataNum = null;
	  String dataName = null;
	  
//	  //Test for Extract Number
//	  String one = "hello23";
//	  String one1 = "hello";
//	  
//	  String two = extractNumber(one);
//	  System.out.println(two);
//	  String two2 = extractNumber(one1);
//	  System.out.println(two2);
      
      Scanner keyboard = new Scanner(System.in);
      
      System.out.println("Enter a title for the data:");
      titleName = keyboard.nextLine();
      System.out.println("You entered: " + titleName);
      
      System.out.println("\nEnter the column 1 header:");
      columnOne = keyboard.nextLine();
      System.out.println("You entered: " + columnOne);
      
      System.out.println("\nEnter the column 2 header:");
      columnTwo = keyboard.nextLine();
      System.out.println("You entered: " + columnTwo);
      
      System.out.println("\nEnter a data point (-1 to stop input):");
      String line = keyboard.nextLine();
      
//    
      //counts commas
      int counter = 0;
         
          for( int i=0; i < line.length(); i++ ) {
              if( line.charAt(i) == ',' ) {
                  counter++;
              } 
          }
          
      while (counter == 0) {
    	  		System.out.println("Error: No comma in string.");
    	  		System.out.println("\nEnter a data point (-1 to stop input):");
    	        String line = keyboard.nextLine();
      }
          
          if (counter == 0) {
      	  		System.out.println("Error: No comma in string.");
          } else if (counter > 1) {
      	  		System.out.println("Error: Too many commas in input.");
    	  	  } else {
    	      }
         
          String[] dataPoint = line.split(",");
    	  		  dataName = dataPoint[0];
    	  		  dataNum = dataPoint[1];
          //checks String for Integer
          Pattern p = Pattern.compile("([0-9])");
          Matcher m = p.matcher(dataNum);

          if(m.find() == false){
        	  	System.out.println("Error: Comma not followed by an integer."); 
          }
          
          System.out.println("Data string: " + dataName + "\nData integer: " + dataNum);

      }
      
  		  
//      String[] dataPoint = line.split(", ");
//      dataName = dataPoint[0];
//      dataNum = dataPoint[1];
      
      //checks String for Integer
      Pattern p = Pattern.compile("([0-9])");
      Matcher m = p.matcher(dataNum);

      if(m.find() == false){
    	  	System.out.println("Error: Comma not followed by an integer."); 
      }
      
      System.out.println("Data string: " + dataName + "\nData integer: " + dataNum);
     
      
             
      return;
   } 
 }
