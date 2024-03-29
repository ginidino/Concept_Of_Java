
# Exercise 3

## Exercise1
Write a program that performs the following operations:
- Prompt the user to enter a series of positive integers. The user will press the enter key after each integer has been input. A maximum of 10 integers will be input. No more than 10 entries should be allowed. If the user enters a negative number the program should quit and print out the following information:
  - All of the numbers that were entered, on a single line, each number separated by a space from the previous one.

Code
```java
public class Exercise01 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		
		int MAX_VALUE = 10;
		int[] values = new int[MAX_VALUE];
		int numValue = 0;
		
		System.out.println("Enter a positive integer or zero. Enter a negative number to quit.");
		int num = Integer.parseInt(reader.nextLine());
		
		while (num >= 0 && numValue < MAX_VALUE) {
			values[numValue++] = num;
			num = Integer.parseInt(reader.nextLine());
		}
		
		System.out.println("The values entered were: ");

		for (int i = 0; i < numValue; i++) {
			System.out.print(values[i] + " ");
		}
	}
}
```
Output
```
Enter a positive integer or zero. Enter a negative number to quit.
1
2
3
4
5
6
7
8
9
0
-1
The values entered were: 
1 2 3 4 5 6 7 8 9 0 
```

## Exercise2
Write a program that performs the following operations:
- Prompt the user to enter a series of positive integers. The user will press the enter key after each integer has been input. A maximum of 50 integers will be input. No more than 50 entries should be allowed. If the user enters a negative number the program should quit and print out the following information:
  - All of the numbers that were entered, on a single line, each number separated by a space from the previous one.
  - The count of the integers entered.
  - The sum of the integers entered.
  - The mean of the integers entered.

Code
```java
import java.util.Scanner;

public class Exercise02 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		
		int MAX_VALUE = 50;
		int[] values = new int[MAX_VALUE];
		int numValue = 0;
		int sum = 0;
		
		System.out.println("Enter a positive integer or zero. Enter a negative number to quit.");
		int num = Integer.parseInt(reader.nextLine());
		
		while (num >= 0 && numValue < MAX_VALUE) {
			values[numValue++] = num;
			num = Integer.parseInt(reader.nextLine());
		}
		
		System.out.println("The values entered were: ");
		
		for (int i = 0; i < numValue; i++) {
			sum += values[i];
		}
		
		double mean = sum / (double) numValue;
		
		System.out.println("The number of the values entered is: " + numValue);
		System.out.println("The sum of the values entered is: " + sum);
		System.out.println("The mean of the values entered is: " + mean);
	}
}
```
Output
```
Enter a positive integer or zero. Enter a negative number to quit.
1
2
3
4
5
6
7
8
9
0
-1
The values entered were: 
The number of the values entered is: 10
The sum of the values entered is: 45
The mean of the values entered is: 4.5
```
## Exercis3
Write a program that performs the following operations:
- Prompt the user to enter a series of strings. The user will press the enter key after each string has been input. A maximum of 10 strings will be input. No more than 10 entries should be allowed. If the user enters the string “quit”, the program should quit and print out the following information:
  - All of the strings that were entered, each one on a separate line. – The number of strings entered.
  - The length of the longest string entered.
  - The length of the shortest string entered.

Code
```java
import java.util.Scanner;

public class Exercise03 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		
		int NUM_STRINGS = 10;
		String[] numString = new String[NUM_STRINGS];
		int max = Integer.MIN_VALUE;
	    int min = Integer.MAX_VALUE;
	    int count = 0;
	    
	    System.out.println("Enter a String. Type ’quit’ to quit.");
	    String word = reader.nextLine();
	    
	    while (!word.equals("quit") && count < NUM_STRINGS) {
	    	numString[count++] = word;
	    	
	    	if (word.length() > max) {
	    		max = word.length();
	    	} else if (word.length() < min) {
	    		min = word.length();
	    	}
	    	
	    	word = reader.nextLine();
	    }
	    System.out.println();
	    
	    for (int i = 0; i < count; i++) {
	    	System.out.println(numString[i]);
	    }
	    
	    System.out.println("Number of strings entered: " + count);
	    System.out.println("Max string length: " + max);
	    System.out.println("Min string length: " + min);
	}
}
```
Output
```
Enter a String. Type ’quit’ to quit.
example
level
output
exercise
leicester
university
store
wallet
quit

example
level
output
exercise
leicester
university
store
wallet
Number of strings entered: 8
Max string length: 10
Min string length: 5
```

## Exercise4
Write a program that performs the following operations:
- Prompt the user to enter a series of integers as a single line of input. Any number of integers might be entered. There will be a space between each input integer.
- When the input line has been entered, output the following information:
  - The count of the integers entered.
  - The sum of the integers entered.
  - The mean of the integers entered.

Code
```java
import java.util.Scanner;

public class Exercise04 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
	
		int sum = 0;
		double mean = 0;
		
		System.out.println("Enter a series of integers on a single line, each separated by a space from the previous.");
		String num = reader.nextLine();
		
		String[] newStr = num.split(" ");
		int[] value = new int[newStr.length];
		
		for (int i = 0; i < value.length; i++) {
			value[i] = Integer.parseInt(newStr[i]);
			sum += value[i];
		}
		mean = sum / (double) value.length;
		
		System.out.println("The number of the values entered is: " + value.length);
	    System.out.println("The sum of the values entered is: " + sum);
	    System.out.println("The mean of the values entered is: " + mean);
	}
}
```
Output
```
Enter a series of integers on a single line, each separated by a space from the previous.
1 2 3 4 5 6 7 8 9 0
The number of the values entered is: 10
The sum of the values entered is: 45
The mean of the values entered is: 4.5
```

## Exercise5
Write a program that performs the following operations:
- Prompt the user to enter a series of integers as a single line of input. Any number of integers might be entered. There will be a space between each input integer.
- When the input line has been entered, output the following:
	- The integers in the reverse order to which they were entered, each one multiplied by 5, all on a single line separated by spaces. For example, if the user enters 2 1 3 0 4, the program will output 20 0 15 5 10 .

Code
```java
import java.util.Scanner;

public class Exercise05 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		
		System.out.println("Enter a series of integers on a single line, each separated by a space from the previous.");
		
		String num = reader.nextLine();
		
		String[] newStr = num.split(" ");
		int[] value = new int[newStr.length];
		
		for (int i = 0; i < value.length; i++) {
			value[i] = 5 * Integer.parseInt(newStr[i]);
		}
		
		for (int i = value.length - 1; i >= 0; i--) {
			System.out.print(value[i] + " ");
		}
	}
}
```
Output
```
Enter a series of integers on a single line, each separated by a space from the previous.
2 1 3 0 4
20 0 15 5 10 
```

## Exercise6
Write a program that performs the following operations:
- Prompt the user to enter a series of integers as a single line of input. Any number of integers might be entered. There will be a space between each input integer.
- Prompt the user to enter another integer. This will be used as an index into the first series of integers, and will count from 1. If the index is not valid, i.e. it is not in the range 1 to number-of-integers- entered, then the program should quit. Any index value lower than 1 is not valid and if, for example, the user enters a series of 6 integers, any index greater than 6 is not valid.
- Output the sum of the values in the series of integers from the index entered in the second input to the end of the series, inclusive. For example, if the user enters the series of integers
1 20 3 -2 7 and the index 3, the program will output 8 (since 3 + −2 + 7 = 8).

Code
```java
import java.util.Scanner;

public class Exercise06 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		
		System.out.println("Enter a series of integers on a single line, each separated by a space from the previous.");
		String num = reader.nextLine();
		
		System.out.println("Now enter an index.");
		int index = Integer.parseInt(reader.nextLine());
		
		String[] newStr = num.split(" ");
		
		if (index >= 1 && index <= newStr.length) {
			int[] value = new int[newStr.length];
			
			for (int i = 0; i < value.length; i++) {
				value[i] = Integer.parseInt(newStr[i]);
			}
			
			int sum = 0;
			
			for (int i = index - 1; i < value.length; i++) {
				sum += value[i];
			}
			System.out.println("The sum from index " + index + " is " + sum + ".");
		} else {
			System.out.println("Invalid index");
		}
	}
}
```
Output
```
Enter a series of integers on a single line, each separated by a space from the previous.
1 20 3 -2 7
Now enter an index.
3
The sum from index 3 is 8.
```

## Exercise7
Write a program that performs the following operations:
- Prompt the user to enter a series of integers as a single line of input. Any number of integers might be entered. There will be a space between each input integer.
- The program should then output the number of values in the series of integers that are duplicated. For example, an input of 1 1 1 would yield the output 3; an input of 1 1 2 would yield the output 2; an input of 1 1 1 2 2 2 1 1 1 would yield the output 9. Note that every instance of any duplicated number is counted.
- The program should then output how many unique numbers exist in the input, i.e., how many numbers are not duplicated.

Code
```java
import java.util.Scanner;

public class Exercise07 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		
		System.out.println("Enter a series of integers on a single line, each separated by a space from the previous.");
		String num = reader.nextLine();
		
		String[] newStr = num.split(" ");
		int[] value = new int[newStr.length];
		
		for (int i = 0; i < value.length; i++) {
			value[i] = Integer.parseInt(newStr[i]);
		}
		
		boolean checkDuplicates = false;
		int count = 0;
		
		for (int i = 0; i < value.length; i++) {
			for (int j = 0; j < value.length; j++) {
				if (i != j) {
					if (value[i] == value[j]) {
						checkDuplicates = true;
					}
				}
			}
			if (checkDuplicates) {
				count++;
				checkDuplicates = false;
			}
		}
		
		System.out.println("There are " + count + " duplicate numbers in the input.");
		System.out.println("There are " + (value.length - count) + " distinct numbers in the input.");
	}
}
```
Output
```
Enter a series of integers on a single line, each separated by a space from the previous.
1 1 2 2 3 2 2 1
There are 7 duplicate numbers in the input.
There are 1 distinct numbers in the input.
```

## Exercise8
Exercise 8
Write a program that performs the following operations:
- Prompt the user to enter a series of positive integers as a single line of input. Any number of integers might be entered. There will be a space between each input integer.
- The program should then output the integers as a set, i.e. with duplicates removed.

Implementation note: Since you will not know in advance how many items should be in the set, you should create an array that is the same size as the input array to hold the set. Since, in this exercise, the input values will be positive, you can fill this set array with negative values. This means you can define a negative value to mean a value in the set array that is not valid (since, in general, the number of valid elements in the set array will be less than the number of values in the input array).

Code
```java
import java.util.Scanner;

public class Exercise08 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		
		System.out.println("Enter a series of integers on a single line, each separated by a space from the previous.");
		String num = reader.nextLine();
		
		String[] newStr = num.split(" ");
		int[] value = new int[newStr.length];
		
		for (int i = 0; i < value.length; i++) {
			value[i] = Integer.parseInt(newStr[i]);
		}
		
		int[] set = new int[value.length];
		
		for (int i = 0; i < value.length; i++) {
			set[i] = -1;
		}
		
		//int count = 0;
		boolean checkDuplicates = false;
		
		for (int i = 0; i < value.length; i++) {
			for (int j = 0; j < value.length; j++) {
				if (set[j] == value[i]) {
					checkDuplicates = true;
				}
			}
			
			if (!checkDuplicates) {
				set[i] = value[i];
			}
			
			checkDuplicates = false;
		}
		
		for (int i = 0; i < set.length; i++) {
			if (set[i] >= 0) {
				System.out.print(set[i] + " ");
			}
		}
	}
}
```
Output
```
Enter a series of integers on a single line, each separated by a space from the previous.
1 1 2 2 3 4 5 5 6
1 2 3 4 5 6 
```

## Exercise9
Write a program that performs the following operations:
-  Prompt the user for a positive integer.
-  Print out a two-dimensional grid of numbers with side length equal to the integer that was entered. For example, if the user enters the value 5, then print out a grid with 5 rows and 5 columns.
-  Each element of the grid should have the value row-position×column-position. For example, if an element has the position (3,2) (i.e. row 3, column 2), its value should be 6.

The output does not need to be formatted. Each grid element can be printed out with no spaces around it. This means that, beyond a certain input number, the output grid will not ‘look square’.

Code
```java
import java.util.Scanner;

public class Exercise09 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		
		System.out.print("Enter a positive integer: ");
		int num = Integer.parseInt(reader.nextLine());
		
		int[][] grid = new int[num][num];
		
		for (int i = 0; i < num; i++) {
			for (int j = 0; j < num; j++) {
				grid[i][j] = i * j;
			}
		}
		
		for (int i = 0; i < num; i++) {
			for (int j = 0; j < num; j++) {
				System.out.print(grid[i][j]);
			}
			System.out.println();
		}
	}
}
```
Output
```
Enter a positive integer: 3
000
012
024
```

## Exercise10
Write a program that performs the following operations:
- Create the following two-dimensional array. This is an array of single digit integers. Do not ask the user to input the array. The array should be declared in the code.
```
0145
3797
1821
```
- Print out the array as shown above, i.e. do not not put spaces or commas, etc. in the output.
- Prompt the user for a number written in the format “xy” with no space in between. This number represents an index in the array. The value of x is the row number and the value of y is the column number.
- Output the array element given by the index that was entered. For example, if the use enters ”23” it should output ’1’. Now set the value of the element addressed by the index to zero and print out the array again. In this example, the array would now look like this:
```
0145
3797
1820
```

Code
```java
import java.util.Scanner;

public class Exercise10 {
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		
		int[][] arr = {{0, 1, 4, 5}, {3, 7, 9, 7}, {1, 8, 2, 1}};
		
		for (int i = 0; i < arr.length; i++) {
			for (int j = 0; j < arr[0].length; j++) {
				System.out.print(arr[i][j]);
			}
			System.out.println();
		}
		
		System.out.print("Enter an index: ");
		String numArr = reader.nextLine();
		
		int row = Character.getNumericValue(numArr.charAt(0));
		int column = Character.getNumericValue(numArr.charAt(1));
		
		System.out.println(arr[row][column]);
		
		arr[row][column] = 0;
		
		for (int i = 0; i < arr.length; i++) {
			for (int j = 0; j < arr[0].length; j++) {
				System.out.print(arr[i][j]);
			}
			System.out.println();
		}
	}
}
```
Output
```
0145
3797
1821
Enter an index: 11
7
0145
3097
1821
```
