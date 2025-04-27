

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
```
#include<stdio.h>
int max_of_four(int a,int b,int c,int d)
{
if(a>b && a>c && a>d)
{
return a;
}
else if(b>a && b>c && b>d)
{
return b;
}
else if(c>a && c>b && c>d)
{
return c;
}
else
{
return d;
}
}
int main()
{
int n1,n2,n3,n4,greater; 
scanf("%d%d%d%d",&n1,&n2,&n3,&n4); 
greater=max_of_four(n1,n2,n3,n4); 
printf("\nThe greatest number is %d",greater);
}
```
Output:
![image](https://github.com/user-attachments/assets/0896a3ac-e7ac-490a-a028-42cf6e692f4f)


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
```
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;

    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            if ((i & j) > a && (i & j) < k) {
                a = i & j;
            }
            if ((i | j) > o && (i | j) < k) {
                o = i | j;
            }
            if ((i ^ j) > x && (i ^ j) < k) {
                x = i ^ j;
            }
        }
    }

    printf("Maximum (i & j) less than k = %d\n", a);
    printf("Maximum (i | j) less than k = %d\n", o);
    printf("Maximum (i ^ j) less than k = %d\n", x);
}

int main() {
    int n, k;
    printf("Enter two integers (n and k): ");
    scanf("%d%d", &n, &k);

    calculate_the_max(n, k);
    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/3ea6dd24-afd1-43f5-997f-22136c36d01d)


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
```
#include <stdio.h>
int main() {
    int noshel, noque;
    printf("Enter the number of shelves and number of queries: \n");
    scanf("%d%d", &noshel, &noque);
    int shelarr[noshel][1000];  
    int nobookarr[noshel];      
    for (int i = 0; i < noshel; i++) {
        nobookarr[i] = 0;
    }
    for (int i = 0; i < noque; i++) {
        int queno;
        printf("Enter query type (1, 2, or 3): \n");
        scanf("%d", &queno);
        if (queno == 1) {
            int shelno, nopage;
            printf("Enter shelf number and number of pages for the book: \n");
            scanf("%d%d", &shelno, &nopage);
            int index = nobookarr[shelno];  
            shelarr[shelno][index] = nopage;  
            nobookarr[shelno]++;  
            printf("Added book with %d pages to shelf %d\n", nopage, shelno);
        }
        else if (queno == 2) {
            int pshelno, pbookno;
            printf("Enter shelf number and book number to query pages: \n");
            scanf("%d%d", &pshelno, &pbookno);
            printf("Number of pages in book %d on shelf %d: %d\n", pbookno, pshelno, shelarr[pshelno][pbookno]);
        }
        else if (queno == 3) {
            int ppshelno;
            printf("Enter shelf number to query total number of books: \n");
            scanf("%d", &ppshelno);
            printf("Total number of books on shelf %d: %d\n", ppshelno, nobookarr[ppshelno]);
        }
    }

    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/489bedca-303e-4741-8937-766978afb0ca)



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
```
#include<stdio.h>

int main() {
    int n;
    scanf("%d", &n);

    int a[n];
    int sum = 0;
    printf("Enter the elements\n");
    for(int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum = sum + a[i];
    }

    printf("Sum of the elements: %d", sum);  

    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/84d2d3c1-4748-4ac7-b145-3a9a602e5560)


 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



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
```
#include<stdio.h>
#include<string.h>
int main()
{
    char str[100];
    fgets(str,sizeof(str),stdin);
    int len=sizeof(str);
    int count=1;
     for(int i=0;i<len-1;i++){
         if(str[i]==' ')
         count++;
         
     }
     printf("Total number of words in the string is :%d",count);
    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/c9292f3b-3cd9-4ea6-943e-f0305dd56f6f)




Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
