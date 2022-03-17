<h1>Resources</h1>
[Debugging](https://en.wikipedia.org/wiki/Debugging)<br>
[Rubber duck debugging](https://www.thoughtfulcode.com/rubber-duck-debugging-psychology/)<br><br>

<p>
Debugging is the process of finding and fixing errors in software that prevents it from running correctly. As you become a more advanced programmer and an industry engineer, you will learn how to use debugging tools such as gdb or built-in tools that IDEs have. However, it’s important to understand the concepts and processes of debugging manually.
</p>

<h2>Quiz</h2>

<h4>Question 0</h4>
Look at the following code<br>

```
carrie@ubuntu:/debugging$ cat main.c                                
#include <stdio.h>                                                                                  

/**                                                                                                 
 * main - debugging example                                                                         
 * Return: 0                                                                                        
 */                                                                                                 
int main(void)                                                                                      
{                                                                                                   
        char *hello = "Hello, World!";                                                              

        for (i = 0; hello[i] != '\0'; i++)                                                          
        {                                                                                           
                printf("%c", hello[i]);                                                             
        }                                                                                           

        printf("\n");                                                                               

        return (0);                                                                                 
}                                                                                                   
carrie@ubuntu:/debugging$
```
<br>

```
carrie@ubuntu:/debugging$ gcc -Wall -Werror -Wextra -pedantic main.
c                                                                                                   
main.c: In function ‘main’:                                                                         
main.c:11:7: error: ‘i’ undeclared (first use in this function)                                     
  for (i = 0; hello[i] != '\0'; i++)                                                                
       ^                                                                                            
main.c:11:7: note: each undeclared identifier is reported only once for each function it appears in
main.c:9:8: error: variable ‘hello’ set but not used [-Werror=unused-but-set-variable]              
  char *hello = "Hello, World!";                                                                    
        ^                                                                                           
cc1: all warnings being treated as errors                                                           
carrie@ubuntu:/debugging$    
```

<br>

In the main.c file, on what line is the first error that the compiler returns?<br>

`
11
`
<br>

<h4>Question 1</h4>
The following code gives this incorrect output.  Which of the following statements about what is causing the error is true?<br>

```
carrie@ubuntu:/debugging$ cat main.c                               
#include <stdio.h>                                                                                 

/**                                                                                                
 * main - debugging example                                                                        
 * Return: 0                                                                                       
 */                                                                                                
int main(void)                                                                                     
{                                                                                                  
        int i;                                                                                     
        int j;                                                                                     

        for (i = 0; i < 10; i++)                                                                   
        {                                                                                          
                j = 0;                                                                             
                while (j < 10)                                                                     
                {                                                                                  
                        printf("%d", j);                                                           
                }                                                                                  
                printf("\n");                                                                      
        }                                                                                          

        return (0);                                                                                
}                                                                                                  
carrie@ubuntu:/debugging$
```
<br>

```
carrie@ubuntu:/debugging$ gcc -Wall -Werror -Wextra -pedantic main.c                                                                                                  
carrie@ubuntu:/debugging$ ./a.out
0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 <...>
^Ccarrie@ubuntu:/debugging$
```
<br>

<li>j never increments so it will always be less than 10
<li>j never increments so it is always going to print 0

<br>

<h4>Question 2</h4>
The following code gives this output. What is the error?<br>

```
carrie@ubuntu:/debugging$ cat main.c                                
#include <stdio.h>                                                                                  

/**                                                                                                 
 * main - debugging example                                                                         
 * Return: 0                                                                                        
 */                                                                                                 
int main(void)                                                                                      
{                                                                                                   
        int i;                                                                                      
        int j;                                                                                      
        int k;                                                                                      

        i = 0;                                                                                      
        j = 1000;                                                                                   
        while (i < j)                                                                               
        {                                                                                           
                k = j / 98;                                                                         
                i = i + k;                                                                          
                printf("%d\n", i);                                                                  
                j == j - 1;                                                                         
        }                                                                                           

        return (0);                                                                                 
}                                                                                                   
carrie@ubuntu:/debugging$
```

<br>

```
carrie@ubuntu:/debugging$ gcc -Wall -Werror -Wextra -pedantic main.
c                                                                                                   
main.c: In function ‘main’:                                                                         
main.c:20:3: error: statement with no effect [-Werror=unused-value]                                 
   j == j - 1;                                                                                      
   ^                                                                                                
cc1: all warnings being treated as errors                                                           
carrie@ubuntu:/debugging$
```
<br>

<li> We want to assign j a new value, not compare it, so it should be j = j - 1 instead of j == j - 1
<br>

<h4>Question 3</h4>
This code doesn't work as intended.<br>

```
#include "main.h"

/**
* main - prints even numbers from 0 to 100
* Return: 0
*/

int main(void)
{
        int i;

        for (i = 0; i < 100; i++)
        {
                if (i % 2 != 0)
                {
                        continue;
                }
                else
                {
                        break;
                }

                printf("%d\n", i);
        }

        return(0);
}
```
<br>
Let’s add printf statements to the code. What information do the printf statements tell us about how our code is executed?
<br>

```
#include "main.h"

/**
* main - prints even numbers from 0 to 100
* Return: 0
*/

int main(void)
{
        int i;

        printf("Before loop\n");

        for (i = 0; i < 100; i++)
        {
                if (i % 2 != 0)
                {
                        printf("i is not even so don't print\n");
                        continue;
                }
                else
                {
                        printf("i is even, break to print\n");
                        break;
                }

                printf("Outside of if/else, still inside for loop\n");

                printf("%d\n", i);
        }

        printf("For loop exited\n");

        return(0);
}
```
<br>
<li>A printf statement shows when the for loop is finished
<li>printf statements shows that break will cause “For loop exited” to print, indicating that the even number is never printed

<h2>Tasks</h2>

<h4>0. Multiple mains</h4>
In most projects, we often give you only one main file to test with. For example, this main file is a test for a <em>postitive_or_negative()</em> function similar to the one you worked with in [an earlier C project](https://github.com/JudahSan/alx-low_level_programming/blob/main/0x01-variables_if_else_while/0-positive_or_negative.c)
<br>

```
carrie@ubuntu:/debugging$ cat main.c
#include "main.h"

/**
* main - tests function that prints if integer is positive or negative
* Return: 0
*/

int main(void)
{
        int i;

        i = 98;
        positive_or_negative(i);

        return (0);
}
carrie@ubuntu:/debugging$
```

<br>

```
carrie@ubuntu:/debugging$ cat main.h
#ifndef MAIN_H
#define MAIN_H

#include <stdio.h>

void positive_or_negative(int i);

#endif /* MAIN_H */
carrie@ubuntu:/debugging$ 
```
<br>

```
carrie@ubuntu:/debugging$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 positive_or_negative.c main.c
carrie@ubuntu:/debugging$ ./a.out
98 is positive
carrie@ubuntu:/debugging$
```

<br>

<p>
Based on the main.c file above, create a file named 0-main.c. This file must test that the function positive_or_negative() gives the correct output when given a case of 0.

You are not coding the solution / function, you’re just testing it! However, you can adapt your function from 0x01. C - Variables, if, else, while - Task #0 to compile with this main file to test locally.

<li>You only need to upload 0-main.c and main.h for this task. We will provide our own positive_or_negative() function.
<li>You are not allowed to add or remove lines of code, you may change only one line in this task.
</p>

<br>

```
#include "main.h"
void positive_or_negative(int i);
/**
* main - tests function that prints if integer is positive or negative
* Return: 0
*/

int main(void)
{
int i;

i = 0;
positive_or_negative(i);

return (0);
}
```
<br>

<h4>1. Like, comment, subscribe/h4>
<p>
Copy this main file. Comment out (don’t delete it!) the part of the code that is causing the output to go into an infinite loop.

<li>Don’t add or remove any lines of code, as we will be checking your line count. You are only allowed to comment out existing code.
<li>You do not have to compile with -Wall -Werror -Wextra -pedantic for this task.
<br><br>

```
carrie@ubuntu:/debugging$ cat 1-main.c
#include <stdio.h>

/**
* main - causes an infinite loop
* Return: 0
*/

int main(void)
{
        int i;

        printf("Infinite loop incoming :(\n");

        i = 0;

        while (i < 10)
        {
                putchar(i);
        }

        printf("Infinite loop avoided! \\o/\n");

        return (0);
}
carrie@ubuntu:/debugging$
```
<br>
Output<br>

```
carrie@ubuntu:/debugging$ gcc -std=gnu89 1-main.c -o 1-main
carrie@ubuntu:/debugging$ ./1-main
Infinite loop incoming :(
Infinite loop avoided! \o/
carrie@ubuntu:/debugging$ wc -l 1-main.c
24 1-main.c
carrie@ubuntu:/debugging$
```

<br>

```
#include <stdio.h>

/**
 * main - causes an infinite loop
 * Return: 0
 **/

int main(void)
{
	int i;

	printf("Infinite loop incoming :(\n");

	/*
	 * i = 0;
	 * while (i < 10)
	 * {
	 * putchar(i);
	 * }
	 **/
	printf("Infinite loop avoided! \\o/\n");

	return (0);
}
```
<br>

<h4>2. 0 > 972?</h4>
<p>
This program prints the largest of three integers.<br>
</p>

```
carrie@ubuntu:/debugging$ cat 2-main.c
#include <stdio.h>
#include "main.h"

/**
* main - prints the largest of 3 integers
* Return: 0
*/

int main(void)
{
        int a, b, c;
        int largest;

        a = 972;
        b = -98;
        c = 0;

        largest = largest_number(a, b, c);

        printf("%d is the largest number\n", largest);

        return (0);
}
carrie@ubuntu:/debugging$
```
<br>

```
carrie@ubuntu:/debugging$ cat 2-largest_number.c
#include "main.h"

/**
 * largest_number - returns the largest of 3 numbers
 * @a: first integer
 * @b: second integer
 * @c: third integer
 * Return: largest number
 */

int largest_number(int a, int b, int c)
{
    int largest;

    if (a > b && b > c)
    {
        largest = a;
    }
    else if (b > a && a > c)
    {
        largest = b;
    }
    else
    {
        largest = c;
    }

    return (largest);
}

carrie@ubuntu:/debugging$
```

<br>

```
carrie@ubuntu:/debugging$ gcc -Wall -Werror -Wextra -pedantic -std=gnu89 2-largest_number.c 2-main.c -o 2-main
carrie@ubuntu:/debugging$ ./2-main
0 is the largest number
carrie@ubuntu:/debugging$

```

<br>

```
#include "main.h"

/**
 * largest_number - returns the largest of 3 numbers
 * @a: first integer
 * @b: second integer
 * @c: third integer
 * Return: largest number
 */

int largest_number(int a, int b, int c)
{
int largest;

	if (a >= b && a >= c)
	{
	largest = a;
	}
	else if (b >= a && b >= c)
	{
	largest = b;
	}
	else
	{
	largest = c;
	}

	return (largest);
}
```

<h4>3. Leap year</h4>
<p>
This program converts a date to the day of year and determines how many days are left in the year, taking leap year into consideration.
</p><br>

```
carrie@ubuntu:/debugging$ cat 3-main_a.c
#include <stdio.h>
#include "main.h"

/**
* main - takes a date and prints how many days are left in the year, taking
* leap years into account
* Return: 0
*/

int main(void)
{
    int month;
    int day;
    int year;

    month = 4;
    day = 01;
    year = 1997;

    printf("Date: %02d/%02d/%04d\n", month, day, year);

    day = convert_day(month, day);

    print_remaining_days(month, day, year);

    return (0);
}

carrie@ubuntu:/debugging$
```

<br>

```
carrie@ubuntu:/debugging$ cat 3-convert_day.c
#include "main.h"

/**
* convert_day - converts day of month to day of year, without accounting
* for leap year
* @month: month in number format
* @day: day of month
* Return: day of year
*/

int convert_day(int month, int day)
{
    switch (month)
    {
        case 2:
            day = 31 + day;
            break;
        case 3:
            day = 59 + day;
            break;
        case 4:
            day = 90 + day;
            break;
        case 5:
            day = 120 + day;
            break;
        case 6:
            day = 151 + day;
            break;
        case 7:
            day = 181 + day;
            break;
        case 8:
            day = 212 + day;
            break;
        case 9:
            day = 243 + day;
            break;
        case 10:
            day = 273 + day;
            break;
        case 11:
            day = 304 + day;
            break;
        case 12:
            day = 334 + day;
            break;
        default:
            break;
    }
    return (day);
}

carrie@ubuntu:/debugging$
```

<br>

```
carrie@ubuntu:/debugging$ cat 3-print_remaining_days.c
#include <stdio.h>
#include "main.h"

/**
* print_remaining_days - takes a date and prints how many days are
* left in the year, taking leap years into account
* @month: month in number format
* @day: day of month
* @year: year
* Return: void
*/

void print_remaining_days(int month, int day, int year)
{
    if ((year % 4 == 0 || year % 400 == 0) && !(year % 100 == 0))
    {
        if (month >= 2 && day >= 60)
        {
            day++;
        }

        printf("Day of the year: %d\n", day);
        printf("Remaining days: %d\n", 366 - day);
    }
    else
    {
        if (month == 2 && day == 60)
        {
            printf("Invalid date: %02d/%02d/%04d\n", month, day - 31, year);
        }
        else
        {
            printf("Day of the year: %d\n", day);
            printf("Remaining days: %d\n", 365 - day);
        }
    }
}

carrie@ubuntu:/debugging$ 
```

<br>

```
carrie@ubuntu:/debugging$ gcc -Wall -Werror -Wextra -pedantic -std=gnu89 3-convert_day.c 3-print_remaining_days.c 3-main_a.c -o 3-main_a 
carrie@ubuntu:/debugging$ ./3-main_a
Date: 04/01/1997
Day of the year: 91
Remaining days: 274
carrie@ubuntu:/debugging$
```
<br>Output looks good for 04/01/1997! Let’s make a new main file 3-main_b.c to try a case that is a leap year: 02/29/2000.<br>

```
carrie@ubuntu:/debugging$ gcc -Wall -Werror -Wextra -pedantic -std=gnu89 3-convert_day.c 3-print_remaining_days.c 3-main_a.c -o 3-main_a 
carrie@ubuntu:/debugging$ ./3-main_a
Date: 04/01/1997
Day of the year: 91
Remaining days: 274
carrie@ubuntu:/debugging$
```
<br>

<p>
? That doesn’t seem right.
<br><br>
Fix the print_remaining_days() function so that the output works correctly for all dates and all leap years.<br><br>

Line count will not be checked for this task.<br>
You can assume that all test cases have valid months (i.e. the value of month will never be less than 1 or greater than 12) and valid days (i.e. the value of day will never be less than 1 or greater than 31).<br>
You can assume that all test cases have valid month/day combinations (i.e. there will never be a June 31st or November 31st, etc.), but not all month/day/year combinations are valid (i.e. February 29, 1991 or February 29, 2427).<br>
</p><br>

```
#include <stdio.h>
#include "main.h"

/**
* print_remaining_days - takes a date and prints how many days are
* left in the year, taking leap years into account
* @month: month in number format
* @day: day of month
* @year: year
* Return: void
*/

void print_remaining_days(int month, int day, int year)
{
if (year % 4 == 0 || year % 400 == 0)
{
if (month >= 3 && day >= 60)
{
day++;
}

printf("Day of the year: %d\n", day);
printf("Remaining days: %d\n", 366 - day);
}
else
{
if (month == 2 && day == 60)
{
printf("Invalid date: %02d/%02d/%04d\n", month, day - 31, year);
}
else
{
printf("Day of the year: %d\n", day);
printf("Remaining days: %d\n", 365 - day);
}
}
}
```