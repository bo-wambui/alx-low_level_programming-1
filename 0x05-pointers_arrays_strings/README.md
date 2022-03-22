<h1>0x05. C - Pointers, arrays and strings</h1>

<h2> Concept and Resources </h2>

[Pointer and Arrays](Pointers_Arrays.md)<br>
[Data Structures](https://www.tutorialspoint.com/data_structures_algorithms/data_structures_basics.htm)<br>
[Data Structures](https://www.geeksforgeeks.org/data-structures/)<br>
[How to Select the Appropriate Data Structure](https://www.careerdrill.com/blog/coding-interview/choosing-the-right-data-structure-to-solve-problems/)<br>

<br><br>

[Arrays](https://www.tutorialspoint.com/cprogramming/c_arrays.htm)<br>
[Pointers](https://www.tutorialspoint.com/cprogramming/c_pointers.htm)<br>
[Strings](https://www.tutorialspoint.com/cprogramming/c_strings.htm)<br>
[Memory layout](https://aticleworld.com/memory-layout-of-c-program/)<br>

<h2>Quiz</h2>

<h4>Question #0
</h4>
What is the size of a pointer to a char (on a 64-bit architecture)<br>

```
8 bytes
```

<h4>Question #1
</h4>
What is the size of a pointer to an int (on a 64-bit architecture)<br>

```
8 bytes
```

<h4>Question #2
</h4>
If we have a variable called var of type int, how can we get its address in memory?<br>

```
&var
```

<h4>Question #3
</h4>
What is the identifier to print an address with printf?<br>

```
%p
```

<h4>Question #4
</h4>
The process of getting the value that is stored in the memory location pointed to by a pointer is called:<br>

```
Dereferencing
```

<h4>Question #5
</h4>
Is it possible to declare a pointer to a pointer?<br>

```
Yes
```

<h4>Question #6
</h4>
What happens when one tries to access an illegal memory location?<br>

```
Segmentation fault
```

<h4>Question #7
</h4>
What is the value of n after the following code is executed?<br>

```
98
```

<h4>Question #8
</h4>
What is the value of n after the following code is executed?<br>

```
98
```

<h4>Question #9
</h4>
What is the value of n after the following code is executed?<br>


```
402
```

<h4>Question #10
</h4>
What is the value of n after the following code is executed?<br>


```
98
```

<h4>Question #11
</h4>
We declare the following variable

```
20 bytes
```

<br>
<h4>Question #12
</h4>
We declare the following variable<br>

```
*(arr + 2)
```

<br>

<h3>Tasks</h3>

<h4>0. 98 Battery st.
</h4>
Write a function that takes a pointer to an int as parameter and updates the value it points to to 98.<br>

<li>Prototype: void reset_to_98(int *n);

```
julien@ubuntu:~/0x05$ cat 0-main.c
#include "main.h"
#include <stdio.h>

/**
 * main - check the code 
 *
 * Return: Always 0.
 */
int main(void)
{
    int n;

    n = 402;
    printf("n=%d\n", n);
    reset_to_98(&n);
    printf("n=%d\n", n);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 0-main.c 0-reset_to_98.c -o 0-98
julien@ubuntu:~/0x05$ ./0-98 
n=402
n=98
julien@ubuntu:~/0x05$ 
```
<br>

```
#include "main.h"

/**
 * reset_to_98 - reset number to 98
 * @n: pointer
 * Return: void
 */

void reset_to_98(int *n)
{
	*n = 98;
}
```

<h4>1. Don't swap horses in crossing a stream

</h4>
Write a function that swaps the values of two integers.<br>

<li>Prototype: void swap_int(int *a, int *b);

```
julien@ubuntu:~/0x05$ cat 1-main.c
#include "main.h"
#include <stdio.h>

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    int a;
    int b;

    a = 98;
    b = 42;
    printf("a=%d, b=%d\n", a, b);
    swap_int(&a, &b);
    printf("a=%d, b=%d\n", a, b);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 1-main.c 1-swap.c -o 1-swap
julien@ubuntu:~/0x05$ ./1-swap 
a=98, b=42
a=42, b=98
julien@ubuntu:~/0x05$
```
<br>

```
#include "main.h"
/**
 * swap_int - swap variable values
 * @a: pointer 1
 * @b: pointer 2
 * Return: void
*/

void swap_int(int *a, int *b)
{
*a += *b;
*b = *a - *b;
*a = *a - *b;
}
```

<h4>2. This report, by its very length, defends itself against the risk of being read
</h4>
<p>Write a function that returns the length of a string.
<br>
<li>Prototype: int _strlen(char *s);<br>
FYI: The standard library provides a similar function: strlen. Run man strlen to learn more.
</p>

```
julien@ubuntu:~/0x05$ cat 2-main.c
#include "main.h"
#include <stdio.h>

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    char *str;
    int len;

    str = "My first strlen!";
    len = _strlen(str);
    printf("%d\n", len);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 2-main.c 2-strlen.c -o 2-strlen
julien@ubuntu:~/0x05$ ./2-strlen 
16
julien@ubuntu:~/0x05$ 
```
<br>

```
#include "main.h"
/**
 * _strlen - find the length of a string
 * @s: pointer to the string to check
 * Return: void
*/


int _strlen(char *s)
{
int i = 0;
while (s[i])
	i++;

return (i);
}
```

<h4>3. I do not fear computers. I fear the lack of them
</h4>
<p>
Write a function that prints a string, followed by a new line, to stdout.
<li>
<li>Prototype: void _puts(char *str);<li>
FYI: The standard library provides a similar function: puts. Run man puts to learn more.

</p>

```
julien@ubuntu:~/0x05$ cat 3-main.c
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    char *str;

    str = "I do not fear computers. I fear the lack of them - Isaac Asimov";
    _puts(str);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 3-main.c 3-puts.c -o 3-puts
julien@ubuntu:~/0x05$ ./3-puts 
I do not fear computers. I fear the lack of them - Isaac Asimov
julien@ubuntu:~/0x05$ 
```
<br>

```
#include "main.h"
/**
 * _puts - prints a string, followed by a new line,
 * @str: pointer to the string to print
 * Return: void
*/


void _puts(char *str)
{
int i = 0;
while (str[i])
{
	_putchar(str[i]);
	i++;
}
_putchar('\n');
}
```

<h4>4. I can only go one way. I've not got a reverse gear
</h4>
<p>
Write a function that prints a string, in reverse, followed by a new line.
<br>
<li>Prototype: void print_rev(char *s);</p>

```
julien@ubuntu:~/0x05$ cat 4-main.c
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    char *str;

    str = "I do not fear computers. I fear the lack of them - Isaac Asimov";
    print_rev(str);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 4-main.c 4-print_rev.c -o 4-print_rev
julien@ubuntu:~/0x05$ ./4-print_rev 
vomisA caasI - meht fo kcal eht raef I .sretupmoc raef ton od I
julien@ubuntu:~/0x05$ 
```
<br>

```
#include "main.h"
/**
 * print_rev - prints reversed string, followed by a new line
 * @s: pointer to the string to print
 * Return: void
*/

void print_rev(char *s)
{
int i = 0;
while (s[i])
	i++;

while (i--)
{
	_putchar(s[i]);
}
_putchar('\n');

}
```

<h4>5. A good engineer thinks in reverse and asks himself about the stylistic consequences of the components and systems he proposes
</h4>
<p>Write a function that reverses a string.<br>

<li>Prototype: void rev_string(char *s);
</p>

```
julien@ubuntu:~/0x05$ cat 5-main.c
#include "main.h"
#include <stdio.h>

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    char s[10] = "My School";

    printf("%s\n", s);
    rev_string(s);
    printf("%s\n", s);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 5-main.c 5-rev_string.c -o 5-rev_string
julien@ubuntu:~/0x05$ ./5-rev_string 
My School
loohcS yM
```
<br>

```
#include "main.h"
/**
 * rev_string - prints reversed string, followed by a new line
 * @s: pointer to the string to print
 * Return: void
*/

void rev_string(char *s)
{

int len, i, half;
char temp;

for (len = 0; s[len] != '\0'; len++)
;

i = 0;

half = len / 2;

while (half--)
{
	temp = s[len - i - 1];
	s[len - i - 1] = s[i];
	s[i] = temp;
	i++;
}

}
```

<h4>6. Half the lies they tell about me aren't true
</h4>
<p>Write a function that prints every other character of a string, starting with the first character, followed by a new line.
<br>
<li>Prototype: void puts2(char *str);
</p>

```
julien@ubuntu:~/0x05$ cat 6-main.c
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    char *str;

    str = "0123456789";
    puts2(str);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 6-main.c 6-puts2.c -o 6-puts2
julien@ubuntu:~/0x05$ ./6-puts2 
02468
julien@ubuntu:~/0x05$ 
```

<br>

```
#include "main.h"
/**
 * puts2 - prints a string, followed by a new line,
 * @str: pointer to the string to print
 * Return: void
*/

void puts2(char *str)
{
int i = 0;
while (str[i] != '\0')
{
	if (i % 2 == 0)
	{
		_putchar(str[i]);
	}

	i++;
}
_putchar('\n');
}
```

<h4>7. Winning is only half of it. Having fun is the other half
</h4>
<p>
Write a function that prints half of a string, followed by a new line.
<br>
<li>Prototype: void puts_half(char *str);
<li>The function should print the second half of the string
<li>If the number of characters is odd, the function should print the last n characters of the string, where n = (length_of_the_string - 1) / 2</p>

```
julien@ubuntu:~/0x05$ cat 7-main.c
#include "main.h"

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    char *str;

    str = "0123456789";
    puts_half(str);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 _putchar.c 7-main.c 7-puts_half.c -o 7-puts_half
julien@ubuntu:~/0x05$ ./7-puts_half 
56789
julien@ubuntu:~/0x05$ 
```

<br>

```
#include "main.h"

/**
 * puts_half - print second half of a string
 * @str: char array string type
 * Description: If odd number of chars, print (length - 1) / 2
 */

void puts_half(char *str)
{
	int i;

	for (i = 0; str[i] != '\0'; i++)
		;

	i++;
	for (i /= 2; str[i] != '\0'; i++)
	{
		_putchar(str[i]);
	}
	_putchar('\n');
}
```

<h4>8. Arrays are not pointers
</h4>
<p>
Write a function that prints n elements of an array of integers, followed by a new line.
<br>
<li>Prototype: void print_array(int *a, int n);
<li>where n is the number of elements of the array to be printed
<li>Numbers must be separated by comma, followed by a space
<li>The numbers should be displayed in the same order as they are stored in the array
<li>You are allowed to use printf</p>

```
julien@ubuntu:~/0x05$ cat 8-main.c
#include "main.h"

/**
 * main - check the code for
 *
 * Return: Always 0.
 */
int main(void)
{
    int array[5];

    array[0] = 98;
    array[1] = 402;
    array[2] = -198;
    array[3] = 298;
    array[4] = -1024;
    print_array(array, 5);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 8-main.c 8-print_array.c -o 8-print_array
julien@ubuntu:~/0x05$ ./8-print_array 
98, 402, -198, 298, -1024
julien@ubuntu:~/0x05$
```

<br>

```
#include "main.h"
#include <stdio.h>

/**
 * print_array - print `n` elements of an array of integers
 * @a: int type array pointer
 * @n: int type integer
 * Description: Numbers must be separated by comma and space.
 * Numbers should be displayed in the same order they are stored in array.
 * You can only use _putchar to print.
 */

void print_array(int *a, int n)
{
	int i;

	i = 0;
	for (n--; n >= 0; n--, i++)
	{
		printf("%d", a[i]);
		if (n > 0)
		{
			printf(", ");
		}
	}
	printf("\n");

}
```

<h4>9. strcpy
</h4>
<p>
<li>Prototype: char *_strcpy(char *dest, char *src);<br>
Write a function that copies the string pointed to by src, including the terminating null byte (\0), to the buffer pointed to by dest.
<br>
<li>Return value: the pointer to dest<br>
FYI: The standard library provides a similar function: strcpy. Run man strcpy to learn more.
</p>

```
julien@ubuntu:~/0x05$ cat 9-main.c
#include "main.h"
#include <stdio.h>

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    char s1[98];
    char *ptr;

    ptr = _strcpy(s1, "First, solve the problem. Then, write the code\n");
    printf("%s", s1);
    printf("%s", ptr);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 9-main.c 9-strcpy.c -o 9-strcpy
julien@ubuntu:~/0x05$ ./9-strcpy 
First, solve the problem. Then, write the code
First, solve the problem. Then, write the code
julien@ubuntu:~/0x05$ 
```

<br>

```
#include "main.h"

/**
 * *_strcpy -  copies the string pointed to by src
 * @dest: char type string
 * @src: char type string
 * Description: Copy the string pointed to by pointer `src` to
 * the buffer pointed to by `dest`
 * Return: Pointer to `dest`
 */

char *_strcpy(char *dest, char *src)
{
	int i = -1;

	do {
		i++;
		dest[i] = src[i];
	} while (src[i] != '\0');

	return (dest);
}
```

<h4>10. Great leaders are willing to sacrifice the numbers to save the people. Poor leaders sacrifice the people to save the numbers
</h4>
<p>
Write a function that convert a string to an integer.
<br><br>
<li>Prototype: int _atoi(char *s);
<li>The number in the string can be preceded by an infinite number of characters
<li>You need to take into account all the - and + signs before the number
<li>If there are no numbers in the string, the function must return 0
<li>You are not allowed to use long
<li>You are not allowed to declare new variables of “type” array
<li>You are not allowed to hard-code special values
<li>We will use the -fsanitize=signed-integer-overflow gcc flag to compile your code.<br>
FYI: The standard library provides a similar function: atoi. Run man atoi to learn more.
</p>

```
julien@ubuntu:~/0x05$ cat 100-main.c
#include "main.h"
#include <stdio.h>

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    int nb;

    nb = _atoi("98");
    printf("%d\n", nb);
    nb = _atoi("-402");
    printf("%d\n", nb);
    nb = _atoi("          ------++++++-----+++++--98");
    printf("%d\n", nb);
    nb = _atoi("214748364");
    printf("%d\n", nb);
    nb = _atoi("0");
    printf("%d\n", nb);
    nb = _atoi("Suite 402");
    printf("%d\n", nb);
    nb = _atoi("         +      +    -    -98 Battery Street; San Francisco, CA 94111 - USA             ");
    printf("%d\n", nb);
    nb = _atoi("---++++ -++ Sui - te -   402 #cisfun :)");
    printf("%d\n", nb);
    return (0);
}
julien@ubuntu:~/0x05$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 -fsanitize=signed-integer-overflow 100-main.c 100-atoi.c -o 100-atoi
julien@ubuntu:~/0x05$ ./100-atoi 
98
-402
-98
214748364
0
402
98
402
julien@ubuntu:~/0x05$ 
```

<br>

```
#include "main.h"

/**
 * _atoi - convert a string to an integer.
 * @s: the string to be comverted.
 *
 *Return: The integer value of the comverted string.
 */

int _atoi(char *s)
{

	int sign = 1;
	unsigned int num = 0;

	do {

		if (*s == '-')
			sign *= -1;

		else if (*s >= '0' && *s <= '9')
			num = (num * 10) + (*s - '0');

		else if (num > 0)
			break;

	} while (*s++);

	return (num * sign);
}
```
<h4>11. Don't hate the hacker, hate the code
</h4>
<p>
Create a program that generates random valid passwords for the program 101-crackme.
<br><br>
<li>You are allowed to use the standard library
<li>You don’t have to pass the betty-style tests (you still need to pass the betty-doc tests)
<li>man srand, rand, time
<li>gdb and objdump can help</p>
<br>



```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

/**
  * main - generates random passwords for 101-crackme
  * Return: zero
  */
int main(void)
{
	int sum;
	char c;

	srand(time(NULL));
	while (sum <= 2645)
	{
		c = rand() % 128;
		sum += c;
		putchar(c);
	}
	putchar(2772 - sum);
	return (0);
}
```