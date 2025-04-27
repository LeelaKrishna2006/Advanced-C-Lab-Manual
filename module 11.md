

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:

      #include <stdio.h>
                
      int findGreatest(int a, int b, int c) {
          if (a >= b && a >= c) {
              return a;
          } else if (b >= a && b >= c) {
              return b;
          } else {
              return c;
          }
      }
      
      int main() {
          int num1, num2, num3, greatest;
      
          printf("Enter three numbers: ");
          scanf("%d %d %d", &num1, &num2, &num3);
      
          greatest = findGreatest(num1, num2, num3);
      
          printf("The greatest number is: %d\n", greatest);
      
          return 0;
      }

Output:

       Enter three numbers: 12 45 33
       The greatest number is: 45
       

Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:

    #include <stdio.h>
    
    int main() {
        int n;
        int maxAnd = 0, maxOr = 0, maxXor = 0;

    printf("Enter the value of n: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int a = i & j;
            int o = i | j;
            int x = i ^ j;

            if (a > maxAnd) maxAnd = a;
            if (o > maxOr) maxOr = o;
            if (x > maxXor) maxXor = x;
        }
    }

    printf("Maximum AND value: %d\n", maxAnd);
    printf("Maximum OR value : %d\n", maxOr);
    printf("Maximum XOR value: %d\n", maxXor);

    return 0;
    }

Output:

        Enter the value of n: 5
        Maximum AND value: 4
        Maximum OR value : 7
        Maximum XOR value: 7


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:

    #include <stdio.h>
    
    void viewItems() {
        printf("Viewing items...\n");
    }
    
    void addItem() {
        printf("Adding item...\n");
    }
    
    void deleteItem() {
        printf("Deleting item...\n");
    }
    
    int main() {
        int choice;

    while (1) {
        printf("\n1. View Items\n2. Add Item\n3. Delete Item\n4. Exit\n");
        printf("Enter your request: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1: viewItems(); break;
            case 2: addItem(); break;
            case 3: deleteItem(); break;
            case 4: return 0;
            default: printf("Invalid request\n");
        }
    }

    return 0;
    }


Output:

     1. View Items
     2. Add Item
     3. Delete Item
     4. Exit
     Enter your request: 2
     Adding item...



Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:

     #include <stdio.h>
     
     int main() {
         int arr[100], n, sum = 0;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];
    }

    printf("Sum of the array elements = %d\n", sum);

    return 0;
}


Output:
    
    Enter the number of elements: 5
    Enter 5 integers:
    1 2 3 4 5
    Sum of the array elements = 15


 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:

    #include <stdio.h>
    
    int main() {
        char sentence[1000];
        int i = 0, words = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    while (sentence[i] != '\0') {
        if ((sentence[i] == ' ' || sentence[i] == '\n' || sentence[i] == '\t') &&
            (i > 0 && sentence[i - 1] != ' ' && sentence[i - 1] != '\n' && sentence[i - 1] != '\t')) {
            words++;
        }
        i++;
    }

    if (i > 0 && sentence[i - 1] != ' ' && sentence[i - 1] != '\n' && sentence[i - 1] != '\t') {
        words++;
    }

    printf("Number of words: %d\n", words);

    return 0;
     }


Output:

    Enter a sentence: This is a sample sentence.
    Number of words: 5




Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
