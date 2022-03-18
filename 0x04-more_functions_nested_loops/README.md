<h1>0x04. C - More functions, more nested loops</h1>

<h2>Resources</h2>
[Nested while loops](https://www.youtube.com/watch?v=Z3iGeQ1gIss)<br>
[Functions](https://www.tutorialspoint.com/cprogramming/c_functions.htm)<br>
[C-programming](https://www.youtube.com/watch?v=qMlnFwYdqIw)<br>
[Function prototype](https://www.geeksforgeeks.org/what-is-the-purpose-of-a-function-prototype/)<br>
[C Header](https://www.tutorialspoint.com/cprogramming/c_header_files.htm)<br>

<h3>Quiz</h3>

<br>

<h4> Question #0</h4>
What is the output of the following piece of code?
<br>

```
int i;

for (i = 48; i < 58; i++)
{
    printf("%c", i);
}
```
<br>

<li>0123456789
<h4> Question #1</h4>
What is the output of the following piece of code?
<br>

```
int i;

i = 0;
while (i < 10)
{
    printf("%d", i % 2);
    i++;
}
```
<br>

<li>0101010101
<h4> Question #2</h4>
What is the output of the following piece of code?
<br>

```
int i;

for (i = 0; i < 10; i++)
{
    printf("%d", i * 2);
}
```
<br>

<li>024681012141618
<h4> Question #3</h4>
What is the output of the following piece of code?
<br>

```
int i;

i = 0;
while (i < 10)
{
    i++;
    printf("%d", i / 2);
}
```
<br>

<li>0112233445
<h4> Question #4
</h4>
What is the output of the following piece of code?
<br>

```
int i;

i = -9;
while (i < 0)
{
    printf("%d", -i);
    i++;
}
```
<br>

<li>987654321
<h4> Question #5
</h4>
What is the output of the following piece of code?


<br>

```
int i;

i = 9;
while (i--)
{
    printf("%d", i);
}
```
<br>

<li>876543210
<h4> Question #6
</h4>
What is the output of the following piece of code?
<br>

```
int i;

i = 9;
while (--i)
{
    printf("%d", i);
}
```
<br>

<li>87654321
<h4> Question #7
</h4>
What is the return value of the following function?
<br>

```
int some_function(void)
{
    printf("%d", 12);
    return (98);
}
```
<br>

<li>98
<h4> Question #8
</h4>
What is the return value of the following function?
<br>

```
int some_function(void)
{
    int i;

    for (i = 0; i < 10; i++)
    {
        printf("%d", i);
    }
    return(i);
}
```
<br>
<li>10

<h3>Tasks</h3>

<h4></h4>0. isupper<br><br>
<p>
Write a function that checks for uppercase character.<br>

<li>Prototype: int _isupper(int c);
<li>Returns 1 if c is uppercase
<li>Returns 0 otherwise<br>
FYI: The standard library provides a similar function: isupper. Run man isupper to learn more.<br>
</p>
<br>

```
julien@ubuntu:~/0x04$ cat 0-main.c
#include "main.h"
#include <stdio.h>

/**
 * main - check the code.
 *
 * Return: Always 0.
 */
int main(void)
{
    char c;

    c = 'A';
    printf("%c: %d\n", c, _isupper(c));
    c = 'a';
    printf("%c: %d\n", c, _isupper(c));
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 0-main.c 0-isupper.c -o 0-isuper
julien@ubuntu:~/0x04$ ./0-isuper 
A: 1
a: 0
julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"

/**
 * _isupper - checks for uppercase character
 * @c: the character to be checked
 * Return: 1 if c is uppercase, 0 otherwise
 */
int _isupper(int c)
{
	return (c >= 'A' && c <= 'Z');
}
```

<h4>1. isdigit</h4>  <br><br>
<p>
Write a function that checks for a digit (0 through 9).

<li>Prototype: int _isdigit(int c);
<li>Returns 1 if c is a digit
<li>Returns 0 otherwise<br>
FYI: The standard library provides a similar function: isdigit. Run man isdigit to learn more.
</p>
<br>

```
julien@ubuntu:~/0x04$ cat 1-main.c 
#include "main.h"
#include <stdio.h>

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    char c;

    c = '0';
    printf("%c: %d\n", c, _isdigit(c));
    c = 'a';
    printf("%c: %d\n", c, _isdigit(c));
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 1-main.c 1-isdigit.c -o 1-isdigit
julien@ubuntu:~/0x04$ ./1-isdigit 
0: 1
a: 0
julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"

/**
 * _isdigit - checks for a digit (0 through 9)
 * @c: int to be checked
 * Return: 1 if c is a digit, 0 otherwise
 */
int _isdigit(int c)
{
	return (c >= '0' && c <= '9');
}
```

<h4>2. Collaboration is multiplication</h4>   <br><br>
<p>
Write a function that multiplies two integers.

<li>Prototype: int mul(int a, int b);
</p>
<br>

```
julien@ubuntu:~/0x04$ cat 2-main.c
#include "main.h"
#include <stdio.h>

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    printf("%d\n", mul(98, 1024));
    printf("%d\n", mul(-402, 4096));
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 2-main.c 2-mul.c -o 2-mul
julien@ubuntu:~/0x04$ ./2-mul 
100352
-1646592
julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"

/**
 * mul - multiplies two integers
 * @a: int to be multiplied to b
 * @b: int to be multiplied to a
 * Return: the result of the operation
 */
int mul(int a, int b)
{
	int c;

	c = a * b;

	return (c);
}
```

<h4>3. The numbers speak for themselves</h4>   <br><br>

<p>Write a function that prints the numbers, from 0 to 9, followed by a new line.

<li>Prototype: void print_numbers(void);
<li>You can only use _putchar twice in your code

</p>
<br>

```
julien@ubuntu:~/0x04$ cat 3-main.c 
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    print_numbers();
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 3-main.c 3-print_numbers.c -o 3-print_numbers
julien@ubuntu:~/0x04$ ./3-print_numbers | cat -e
0123456789$
julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"

/**
 * print_numbers - prints the numbers, from 0 to 9,
 * followed by a new line
 */
void print_numbers(void)
{
	int i;

	for (i = 0; i < 10; i++)
	{
		_putchar(i + '0');
	}

	_putchar('\n');
}
```
<h4>4. I believe in numbers and signs</h4>   <br><br>

<p>

Write a function that prints the numbers, from 0 to 9, followed by a new line.<br>

<li>Prototype: void print_most_numbers(void);<br>
<li>Do not print 2 and 4<br>
<li>You can only use _putchar twice in your code

</p>
<br>

```
julien@ubuntu:~/0x04$ cat 4-main.c
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    print_most_numbers();
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 4-main.c 4-print_most_numbers.c -o 4-print_most_numbers
julien@ubuntu:~/0x04$ ./4-print_most_numbers 
01356789
julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"

/**
 * print_most_numbers - prints the numbers, from 0 to 9,
 * except 2 and 4, followed by a new line
 */
void print_most_numbers(void)
{
	int i;

	for (i = 0; i < 10; i++)
	{
		if (i != 2 && i != 4)
		{
			_putchar(i + '0');
		}
	}

	_putchar('\n');
}

```
<h4>5. Numbers constitute the only universal language</h4>   <br><br>

<p>Write a function that prints 10 times the numbers, from 0 to 14, followed by a new line.

<li>Prototype: void more_numbers(void);
<li>You can only use _putchar three times in your code<br>

</p>
<br>

```
julien@ubuntu:~/0x04$ cat 5-main.c
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    more_numbers();
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 5-main.c 5-more_numbers.c -o 5-more_numbers
julien@ubuntu:~/0x04$ ./5-more_numbers 
01234567891011121314
01234567891011121314
01234567891011121314
01234567891011121314
01234567891011121314
01234567891011121314
01234567891011121314
01234567891011121314
01234567891011121314
01234567891011121314
julien@ubuntu:~/0x04
```

<br>

```
#include "main.h"

/**
 * more_numbers - prints 10 times the numbers, from 0 to 14
 * followed by a new line
 */
void more_numbers(void)
{
	int i, j;

	for (i = 0; i < 10; i++)
	{
		for (j = 0; j < 15; j++)
		{
			if (j >= 10)
				_putchar(j / 10 + '0');
			_putchar(j % 10 + '0');
		}
		_putchar('\n');
	}
}

```
<br>
<h4>6. The shortest distance between two points is a straight line</h4>    <br><br>

<p>Write a function that draws a straight line in the terminal.

<li>Prototype: void print_line(int n);
<li>You can only use _putchar function to print
<li>Where n is the number of times the character _ should be printed
<li>The line should end with a \n
<li>If n is 0 or less, the function should only print \n

</p>
<br>

```
julien@ubuntu:~/0x04$ cat 6-main.c
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    print_line(0);
    print_line(2);
    print_line(10);
    print_line(-4);
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 6-main.c 6-print_line.c -o 6-lines
julien@ubuntu:~/0x04$ ./6-lines | cat -e
$
__$
__________$
$
julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"

/**
 * print_line - draws a straight line in the terminal
 * @n: number of times the character _ should be printed
 */
void print_line(int n)
{
	if (n <= 0)
	{
		_putchar('\n');
	} else
	{
		int i;

		for (i = 1; i <= n; i++)
		{
			_putchar('_');
		}
		_putchar('\n');
	}

}

```
<h4>7. I feel like I am diagonally parked in a parallel universe</h4>   <br><br>

<p>Write a function that draws a diagonal line on the terminal.

<li>Prototype: void print_diagonal(int n);
<li>You can only use _putchar function to print
<li>Where n is the number of times the character \ should be printed
<li>The diagonal should end with a \n
<li>If n is 0 or less, the function should only print a \n

</p>
<br>

```
julien@ubuntu:~/0x04$ cat 7-main.c
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    print_diagonal(0);
    print_diagonal(2);
    print_diagonal(10);
    print_diagonal(-4);
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 7-main.c 7-print_diagonal.c -o 7-diagonals
julien@ubuntu:~/0x04$ ./7-diagonals | cat -e
$
\$
 \$
\$
 \$
  \$
   \$
    \$
     \$
      \$
       \$
        \$
         \$
$
julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"

/**
 * print_diagonal - draws a diagonal line on the terminal
 * @n: number of times the character \ should be printed
 */
void print_diagonal(int n)
{
	if (n <= 0)
	{
		_putchar('\n');
	} else
	{
		int i, j;

		for (i = 0; i < n; i++)
		{
			for (j = 0; j < n; j++)
			{
				if (j == i)
					_putchar('\\');
				else if (j < i)
					_putchar(' ');
			}
			_putchar('\n');
		}
	}
}

```
<h4>8. You are so much sunshine in every square inch</h4>   <br><br>

<p>Write a function that prints a square, followed by a new line.

<li>Prototype: void print_square(int size);
<li>You can only use _putchar function to print
<li>Where size is the size of the square
<li>If size is 0 or less, the function should print only a new line
<li>Use the character # to print the square

</p>
<br>

```
julien@ubuntu:~/0x04$ cat 8-main.c 
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    print_square(2);
    print_square(10);
    print_square(0);
    return (0);
}

julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 8-main.c 8-print_square.c -o 8-squares
julien@ubuntu:~/0x04$ ./8-squares 
##
##
##########
##########
##########
##########
##########
##########
##########
##########
##########
##########

julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"

/**
 * print_square - prints a square, followed by a new line;
 * @size: size of the square
 */
void print_square(int size)
{
	if (size <= 0)
	{
		_putchar('\n');
	} else
	{
		int i, j;

		for (i = 0; i < size; i++)
		{
			for (j = 0; j < size; j++)
			{
				_putchar('#');
			}
			_putchar('\n');
		}
	}
}

```
<h4>9. Fizz-Buzz</h4>   <br><br>
<p>The “Fizz-Buzz test” is an interview question designed to help filter out the 99.5% of programming job candidates who can’t seem to program their way out of a wet paper bag.
<br><br>
Write a program that prints the numbers from 1 to 100, followed by a new line. But for multiples of three print Fizz instead of the number and for the multiples of five print Buzz. For numbers which are multiples of both three and five print FizzBuzz.
<br><br>
<li>Each number or word should be separated by a space
<li>You are allowed to use the standard library

</p>
<br>

```
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 9-fizz_buzz.c -o 9-fizz_buzz
julien@ubuntu:~/0x04$ ./9-fizz_buzz 
1 2 Fizz 4 Buzz Fizz 7 8 Fizz Buzz 11 Fizz 13 14 FizzBuzz 16 17 Fizz 19 Buzz Fizz 22 23 Fizz Buzz 26 Fizz 28 29 FizzBuzz 31 32 Fizz 34 Buzz Fizz 37 38 Fizz Buzz 41 Fizz 43 44 FizzBuzz 46 47 Fizz 49 Buzz Fizz 52 53 Fizz Buzz 56 Fizz 58 59 FizzBuzz 61 62 Fizz 64 Buzz Fizz 67 68 Fizz Buzz 71 Fizz 73 74 FizzBuzz 76 77 Fizz 79 Buzz Fizz 82 83 Fizz Buzz 86 Fizz 88 89 FizzBuzz 91 92 Fizz 94 Buzz Fizz 97 98 Fizz Buzz
julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"
#include <stdio.h>

/**
 * main - prints the numbers from 1 to 100, followed by a new line
 * but for multiples of three prints Fizz instead of the number
 * and for the multiples of five prints Buzz
 * Return: Always 0 (Success)
 */
int main(void)
{
	int i;

	for (i = 1; i <= 100; i++)
	{
		if (i % 3 == 0 && i % 5 != 0)
		{
			printf(" Fizz");
		} else if (i % 5 == 0 && i % 3 != 0)
		{
			printf(" Buzz");
		} else if (i % 3 == 0 && i % 5 == 0)
		{
			printf(" FizzBuzz");
		} else if (i == 1)
		{
			printf("%d", i);
		} else
		{
			printf(" %d", i);
		}
	}
	printf("\n");

	return (0);
}

```

<h4>10. Triangles</h4>   <br><br> 

<p>Write a function that prints a triangle, followed by a new line.<br>

<br>Prototype: void print_triangle(int size);
<br>You can only use _putchar function to print
<br>Where size is the size of the triangle
<br>If size is 0 or less, the function should print only a new line
<br>Use the character # to print the triangle

</p>
<br>

```
julien@ubuntu:~/0x04$ cat 10-main.c 
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    print_triangle(2);
    print_triangle(10);
    print_triangle(1);
    print_triangle(0);
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 10-main.c 10-print_triangle.c -o 10-triangles
julien@ubuntu:~/0x04$ ./10-triangles 
 #
##
         #
        ##
       ###
      ####
     #####
    ######
   #######
  ########
 #########
##########
#

julien@ubuntu:~/0x04$ ./10-triangles | tr ' ' . | cat -e
.#$
##$
.........#$
........##$
.......###$
......####$
.....#####$
....######$
...#######$
..########$
.#########$
##########$
#$
$
julien@ubuntu:~/0x04$
```

<br>

```
#include "main.h"

/**
 * print_triangle - prints a triangle, followed by a new line
 * @size: size of the triangle
 */
void print_triangle(int size)
{
	if (size <= 0)
	{
		_putchar('\n');
	} else
	{
		int i, j;

		for (i = 1; i <= size; i++)
		{
			for (j = i; j < size; j++)
			{
				_putchar(' ');
			}

			for (j = 1; j <= i; j++)
			{
				_putchar('#');
			}

			_putchar('\n');
		}
	}
}

```
<br>
<h4>11. The problem of distinguishing prime numbers from composite numbers and of resolving the latter into their prime factors is known to be one of the most important and useful in arithmetic</h4>   <br><br>

<p>The prime factors of 1231952 are 2, 2, 2, 2, 37 and 2081.<br><br>

Write a program that finds and prints the largest prime factor of the number 612852475143, followed by a new line.<br><br>

<li>You are allowed to use the standard library
<li>Your program will be compiled with this command: gcc -Wall -pedantic -Werror -Wextra -std=gnu89 100-prime_factor.c -o 100-prime_factor -lm
</p>
<br>

```
#include <stdio.h>
#include <math.h>

/**
 * main - finds and prints the largest prime factor of the number 612852475143
 * followed by a new line
 * Return: Always 0 (Success)
 */
int main(void)
{
	long int n;
	long int max;
	long int i;

	n = 612852475143;
	max = -1;

	while (n % 2 == 0)
	{
		max = 2;
		n /= 2;
	}

	for (i = 3; i <= sqrt(n); i = i + 2)
	{
		while (n % i == 0)
		{
			max = i;
			n = n / i;
		}
	}

	if (n > 2)
		max = n;

	printf("%ld\n", max);

	return (0);
}

```
<h4>12. Numbers have life; they're not just symbols on paper</h4>   <br><br>

<p>Write a function that prints an integer.<br>
<li>Prototype: void print_number(int n);
<li>You can only use _putchar function to print
<li>You are not allowed to use long
<li>You are not allowed to use arrays or pointers
<li>You are not allowed to hard-code special values
</p>
<br>

```
julien@ubuntu:~/0x04$ cat 101-main.c
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    print_number(98);
    _putchar('\n');
    print_number(402);
    _putchar('\n');
    print_number(1024);
    _putchar('\n');
    print_number(0);
    _putchar('\n');
    print_number(-98);
    _putchar('\n');
    return (0);
}
julien@ubuntu:~/0x04$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 101-main.c 101-print_number.c -o 101-print_numbers
julien@ubuntu:~/0x04$ ./101-print_numbers 
98
402
1024
0
-98
julien@ubuntu:~/0x04$ 
```

<br>

```
#include "main.h"

/**
 * print_number - prints an integer
 * @n: integer to be printed
 */
void print_number(int n)
{
	unsigned int n1;

	if (n < 0)
	{
		n1 = -n;
		_putchar('-');
	} else
	{
		n1 = n;
	}

	if (n1 / 10)
	{
		print_number(n1 / 10);
	}

	_putchar((n1 % 10) + '0');
}

```
<h4></h4>   <br><br>
  <p>

</p>
<br>

```

```

<br>

```

```