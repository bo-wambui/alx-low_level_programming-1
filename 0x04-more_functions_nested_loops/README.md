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

<h4></h4>   <br><br>

<p>

</p>
<br>

```

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
<h4></h4>   <br><br>

<p>

</p>
<br>

```

```

<br>

```

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
<h4></h4>    <br><br>

<p>

</p>
<br>

```

```

<br>

```

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
<h4></h4>   <br><br>

<p>

</p>
<br>

```

```

<br>

```

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

<h4></h4>   <br><br> 

<p>

</p>
<br>

```

```

<br>

```

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
<h4></h4>   <br><br>

<p>

</p>
<br>

```

```

<br>

```

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