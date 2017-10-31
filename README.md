# Balanced-braces-
#This program reads a string and checks if the brackets (round,square or curly) are Balanced.  
import java.util.Scanner;
import java.util.Stack;

public class isBalanced{
	
	public static void main(String[] args) {
        boolean inputbracket = false; 
        Stack<Character> input1 = new Stack<Character>(); //creating stack for "("
		Stack<Character> input2 = new Stack<Character>(); //creating stack for "["
		Stack<Character> input3 = new Stack<Character>(); //creating stack for "{"
		System.out.print("Enter String to check: "); //prompts user for a string 
        Scanner scanner = new Scanner(System.in); 
        String sinput = scanner.nextLine();
		boolean state = false;	//Assigns state
        char[] c = sinput.toCharArray();
		for (int i = 0; i < c.length; i++) {
			if(c[i] == '(' ){ //checks through the string and for a bracket
				input1.push(c[i]); //Pushes the bracket into the stack
				inputbracket = true; //returns true since bracket is in the input 
			}
			else if(c[i] == '['){ //checks through the string and for a bracket
				input2.push(c[i]);//Pushes the bracket into the stack
				inputbracket = true; //returns true since bracket is in the input
			}
            else if(c[i] == '{'){ //checks through the string and for a bracket
				input3.push(c[i]); //Pushes the bracket into the stack
				inputbracket = true; //returns true since bracket is in the input
			}		
			else if(c[i] == ')'){
				inputbracket = true;
				if(input1.empty() == true){ //checks if stack is empty before it pops
					state = true; // if stack is empty then the state is 
				}
				else{
					input1.pop();// if stack is not empty then Pop
			}	
			else if(c[i] == ']'){
				inputbracket = true;
				if(input2.empty() == true){ //checks if stack is empty before it pops
					state = true; //if stack is empty then the state is 
				}
				else{
					input2.pop(); // if stack is not empty then Pop
				}		
			}	
			else if(c[i] == '}'){
				inputbracket = true;
				if(input3.empty() == true){ //checks if stack is empty before it pops
					state = true; // if stack is empty then the state is 
				}
				else{
					input3.pop(); // if stack is not empty then Pop 
				}	
			}
		}
		if ( inputbracket == false){ //checks if input has brackets
			System.out.println("String doesn't contain any Brackets ");	  
		}else if ( inputbracket == true && state==false && input1.empty() == true && input2.empty() == true && input2.empty() == true ){
            System.out.println("String is balanced"); //outputs Valid string 
        }else {
            System.out.println("String is not Balanced "); //outputs Valid string
        scanner.close(); //Close scanner
		}
	}
	}
	


