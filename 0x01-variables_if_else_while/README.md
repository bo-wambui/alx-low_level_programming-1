<h1>Variables, if, else, while</h1>






<h3>Resources</h3>

[Keywords and Identifiers](https://publications.gbdirect.co.uk//c_book/chapter2/keywords_and_identifiers.html) <br>
[Integral Types](https://publications.gbdirect.co.uk//c_book/chapter2/integral_types.html) <br>
[Arithmetic Operators in C](https://www.tutorialspoint.com/cprogramming/c_arithmetic_operators.htm) <br>
[if...else statement](https://www.tutorialspoint.com/cprogramming/if_else_statement_in_c.htm) <br>
[Relational Operators in C](https://www.tutorialspoint.com/cprogramming/c_relational_operators.htm) <br>
[while loop in C](https://www.tutorialspoint.com/cprogramming/c_while_loop.htm) <br>
Video [while loop](https://www.youtube.com/watch?v=Ju1LYO9pkaI&t=2s&ab_channel=Simplified) <br> `


<h2>Questions</h4>


<ol>

<li> Question #0<br>
What is the size of the unsigned int data type?<br>
<em>4 byte</em>
<li>Question #1<br>
What is the size of the char data type?<br>
<em>1 byte</em> <br>
<li>Question #2<br>
What is the size of the float data type?<br>
<em>4 bytes</em>
<li>Question #3<br>
Which of the following are valid if statements in ANSI C and Betty-compliant? (Considering a and b two variables of type int)<br>


```
if (a > b)
{
  return (a);
}
```
<br>

```
if (a > b)
  return (a);
```

<br>
<li>Question #4<br>
Which of the following are valid for statements in ANSI C and Betty-compliant? (Considering a and b two variables of type int) <br>


```
for (a = 0; a < b; a++)
{
    printf("%d\n", a);
}
		  
```
<br>		 

	
```
for (a = 0; a < b; a++)
    printf("%d\n", a);
```
		 
<br>
	
```
a = 0;
for (; a < b;)
{
    printf("%d\n", a++);
}
```



<li>Question #5<br>
Which of the following are valid while or do/while statements in ANSI C and Betty-compliant? (Considering a and b two variables of type int)<br>
	
```
a = 0;
while (a < b)
{
    printf("%d\n", a);
    a++;
}
```
<br>

```
a = 0;
do {
    printf("%d\n", a);
    a++;
} while (a < b);
```
<br>
	
```
a = 0;
while (a < b)
    printf("%d\n", a++);
```
<br>
</ol>

<h2>Tasks</h2>

<ol>
<li>[0. Positive anything is better than negative nothing<br>

This program will assign a random number to the variable n each time it is executed. Complete the source code in order to print whether the number stored in the variable n is positive or negative.<br>

You can find the source code here<br>
The variable n will store a different value every time you will run this program<br>
You don’t have to understand what rand, srand, RAND_MAX do. Please do not touch this code<br>
The output of the program should be:<br>
The number, followed by<br>
if the number is greater than 0: is positive<br>
if the number is 0: is zero<br>
if the number is less than 0: is negative<br>
followed by a new line<br>

```
#include <stdlib.h>
#include <time.h>
#include <stdio.h>

/**
 * main - Prints if number is positive, zero or negative
 *
 * Return: Always (Success)
 */
int main(void)
{
	int n;

	srand(time(0));
	n = rand() - RAND_MAX / 2;

	if (n > 0)
	{
		printf("%d is positive\n", n);
	}
	else if (n == 0)
	{
		printf("%d is zero\n", n);
	}
	else
	{
		printf("%d is negative\n", n);
	}

	return (0);
}

```

<li>[1. The last digit<br>

This program will assign a random number to the variable n each time it is executed. Complete the source code in order to print the last digit of the number stored in the<br> variable n.<br>

You can find the source code here<br>
The variable n will store a different value every time you run this program<br>
You don’t have to understand what rand, srand, and RAND_MAX do. Please do not touch this code<br>
The output of the program should be:<br>
The string Last digit of, followed by<br>
n, followed by<br>
the string is, followed by<br>
if the last digit of n is greater than 5: the string and is greater than 5<br>
if the last digit of n is 0: the string and is 0<br>
if the last digit of n is less than 6 and not 0: the string and is less than 6 and not 0<br>
followed by a new line<br>

```
#include <stdlib.h>
#include <time.h>
#include <stdio.h>

/**
 * main - Prints a text according number
 *
 * Return: Always (Success)
 */
int main(void)
{
	int n, lastd;

	srand(time(0));
	n = rand() - RAND_MAX / 2;
	lastd = n % 10;

	if (lastd > 5)
	{
		printf("Last digit of %d is %d and is greater than 5\n", n, lastd);
	}
	else if (lastd == 0)
	{
		printf("Last digit of %d is %d and is 0\n", n, lastd);
	}
	else if (lastd < 6 && lastd != 0)
	{
		printf("Last digit of %d is %d and is less than 6 and not 0\n", n, lastd);
	}

	return (0);
}

```

<li>[2. I sometimes suffer from insomnia. And when I can't fall asleep, I play what I call the alphabet game<br>

Write a program that prints the alphabet in lowercase, followed by a new line.<br>

You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)<br>
All your code should be in the main function<br>
You can only use putchar twice in your code<br>

```
#include <stdio.h>

/**
 * main - Prints the alphabetic
 *
 * Return: Always (Success)
 */
int main(void)
{
	char c;

	for (c = 'a'; c <= 'z'; c++)
		putchar(c);

	putchar('\n');
	return (0);
}

```

<li>[3. alphABET<br>

Write a program that prints the alphabet in lowercase, and then in uppercase, followed by a new line.<br>

You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)<br>
All your code should be in the main function<br>
You can only use putchar three times in your code<br>

```
#include <stdio.h>

/**
 * main - Prints the alphabetic in lower and upper case
 *
 * Return: Always (Success)
 */
int main(void)
{
	char c;

	for (c = 'a'; c <= 'z'; c++)
	{
		putchar(c);
	}

	for (c = 'A'; c <= 'Z'; c++)
	{
		putchar(c);
	}

	putchar('\n');

	return (0);
}

```

<li>[4. When I was having that alphabet soup, I never thought that it would pay off<br>

Write a program that prints the alphabet in lowercase, followed by a new line.<br>

Print all the letters except q and e<br>
You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)<br>
All your code should be in the main function<br>
You can only use putchar twice in your code<br>

```
#include <stdio.h>

/**
  * main - Prints some letters of alphabet
  *
  * Return: Always (Success)
  */
int main(void)
{
	char c;

	for (c = 'a'; c <= 'z'; c++)
	{
		if (c != 'e' && c != 'q')
		{
			putchar(c);
		}
	}

	putchar('\n');

	return (0);
}

```

<li>[5. Numbers<br>

Write a program that prints all single digit numbers of base 10 starting from 0, followed by a new line.<br>

All your code should be in the main function<br>

```
#include <stdio.h>

/**
  * main - Prints the numbers since 0 to 9
  *
  * Return: Always (Success)
  */
int main(void)
{
	char n;

	for (n = '0'; n <= '9'; n++)
	{
		putchar(n);
	}

	putchar('\n');

	return (0);
}

```

<li>[6. Numberz<br>

Write a program that prints all single digit numbers of base 10 starting from 0, followed by a new line.<br>

You are not allowed to use any variable of type char<br>
You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)<br>
You can only use putchar twice in your code<br>
All your code should be in the main function<br>

```
#include <stdio.h>

/**
  * main - Prints the numbers since 0 to 9
  *
  * Return: Always (Success)
  */
int main(void)
{
	char n;

	for (n = '0'; n <= '9'; n++)
	{
		putchar(n);
	}

	putchar('\n');

	return (0);
}

```

<li>[7. Smile in the mirror
mandatory
Write a program that prints the lowercase alphabet in reverse, followed by a new line.

You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)
All your code should be in the main function
You can only use putchar twice in your code

```
#include <stdio.h>

/**
  * main - Prints the alphabet at reverse
  *
  * Return: Always (Success)
  */
int main(void)
{
	char c;

	for (c = 'z'; c >= 'a'; c--)
	{
		putchar(c);
	}

	putchar('\n');

	return (0);
}

```

<li>[8. Hexadecimal<br>

Write a program that prints all the numbers of base 16 in lowercase, followed by a new line.<br>

You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)<br>
All your code should be in the main function<br>
You can only use putchar three times in your code<br>

```
#include <stdio.h>

/**
  * main - Prints a hexadecimal string
  *
  * Return: Always (Success)
  */
int main(void)
{
	char c;

	for (c = '0'; c <= '9'; c++)
	{
		putchar(c);
	}

	for (c = 'a'; c <= 'f'; c++)
	{
		putchar(c);
	}

	putchar('\n');

	return (0);
}
```

<li>[9. Patience, persistence and perspiration make an unbeatable combination for success<br>

Write a program that prints all possible combinations of single-digit numbers.<br>

Numbers must be separated by ,, followed by a space<br>
Numbers should be printed in ascending order<br>
You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)<br>
All your code should be in the main function<br>
You can only use putchar four times maximum in your code<br>
You are not allowed to use any variable of type char

```
#include <stdio.h>

/**
  * main - Prints a serie of numbers with commas
  *
  * Return: Always (Success);
  */
int main(void)
{
	int c;

	for (c = '0'; c <= '9'; c++)
	{
		putchar(c);

		if (c != '9')
		{
			putchar(',');
			putchar(' ');
		}
	}

	putchar('\n');

	return (0);
}

```

<li>[10. Inventing is a combination of brains and materials. The more brains you use, the less material you need<br>

Write a program that prints all possible different combinations of two digits.<br>

Numbers must be separated by ,, followed by a space<br>
The two digits must be different<br>
01 and 10 are considered the same combination of the two digits 0 and 1<br>
Print only the smallest combination of two digits<br>
Numbers should be printed in ascending order, with two digits<br>
You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)<br>
You can only use putchar five times maximum in your code<br>
You are not allowed to use any variable of type char<br>
All your code should be in the main function<br>

```
#include <stdio.h>

/**
  * main - Prints combination of numbers
  *
  * Return: Always (Success)
  */
int main(void)
{
	int c, i;

	for (c = '0'; c <= '9'; c++)
	{
		for (i = '0'; i <= '9'; i++)
		{
			if (c < i)
			{
				putchar(c);
				putchar(i);

				if (c != '8' || (c == '8' && i != '9'))
				{
					putchar(',');
					putchar(' ');
				}
			}
		}
	}

	putchar('\n');

	return (0);
}

```

<li>11. The success combination in business is: Do what you do better... and: do more of what you do...<br>

Write a program that prints all possible different combinations of three digits.<br>

Numbers must be separated by ,, followed by a space<br>
The three digits must be different<br>
012, 120, 102, 021, 201, 210 are considered the same combination of the three digits 0, 1 and 2<br>
Print only the smallest combination of three digits<br>
Numbers should be printed in ascending order, with three digits<br>
You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)<br>
You can only use putchar six times maximum in your code<br>
You are not allowed to use any variable of type char<br>
All your code should be in the main function<br>

```
#include <stdio.h>

/**
  * main - Prints 3 combination of numbers
  *
  * Return: Always (Success)
  */
int main(void)
{
	int c, i, k;

	for (c = '0'; c <= '9'; c++)
	{
		for (i = '0'; i <= '9'; i++)
		{
			for (k = '0'; k <= '9'; k++)
			{
				if (c < i && i < k)
				{
					putchar(c);
					putchar(i);
					putchar(k);

					if (c != '7')
					{
						putchar(',');
						putchar(' ');
					}
				}
			}
		}
	}

	putchar('\n');

	return (0);
}

```

<li>12. Software is eating the World<br>

Write a program that prints all possible combinations of two two-digit numbers.<br>

The numbers should range from 0 to 99<br>
The two numbers should be separated by a space<br>
All numbers should be printed with two digits. 1 should be printed as 01<br>
The combination of numbers must be separated by comma, followed by a space<br>
The combinations of numbers should be printed in ascending order<br>
00 01 and 01 00 are considered as the same combination of the numbers 0 and 1<br>
You can only use the putchar function (every other function (printf, puts, etc…) is forbidden)<br>
You can only use putchar eight times maximum in your code<br>
You are not allowed to use any variable of type char<br>
All your code should be in the main function<br>

```
#include <stdio.h>

/**
  * main - Prints 3 combination of numbers
  *
  * Return: Always (Success)
  */
int main(void)
{
	int c, i, k, j;

	for (c = 48; c <= 57; c++)
	{
		for (i = 48; i <= 57; i++)
		{
			for (k = 48; k <= 57; k++)
			{
				for (j = 48; j <= 57; j++)
				{
					if (((k + j) > (c + i) &&  k >= c) || c < k)
					{
						putchar(c);
						putchar(i);
						putchar(' ');
						putchar(k);
						putchar(j);

					if (c + i + k + j == 227 && c == 57)
					{
					break;
					}
					else
					{
					putchar(',');
					putchar(' ');
					}
					}
				}
			}
		}
	}

	putchar('\n');

	return (0);
}

```


</ol>
