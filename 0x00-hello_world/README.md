Resources: <br>

https://en.wikipedia.org/wiki/Dennis_Ritchie<br>
https://www.youtube.com/watch?v=de2Hsvxaf8M&ab_channel=Computerphile<br>
https://www.youtube.com/watch?v=smGalmxPVYc&ab_channel=ChrisHawkes<br>
https://www.youtube.com/watch?v=rk2fK2IIiiQ&ab_channel=JonathanEngelsma<br>
https://www.youtube.com/watch?v=FwpP_MsZWnU&ab_channel=JonathanEngelsma<br>
https://www.youtube.com/watch?v=VDslRumKvRA&ab_channel=HowTo<br>
https://github.com/holbertonschool/Betty/wiki<br>
http://harmful.cat-v.org/software/c++/linus<br>
https://twitter.com/unix_byte/status/1024147947393495040?s=21<br>

<h2>Quiz</h2>

<h2>Scripts</h2>

<ol>
<li>[0. Preprocessor<br>

Write a script that runs a C file through the preprocessor and save the result into another file.<br>

The C file name will be saved in the variable $CFILE<br>
The output should be saved in the file c<br>

`#!/bin/bash<br>
gcc -E $CFILE -o c`

<li>[1. Compiler<br>

Write a script that compiles a C file but does not link.<br>

The C file name will be saved in the variable $CFILE<br>
The output file should be named the same as the C file, but with the extension .o instead of .c.<br>
Example: if the C file is main.c, the output file should be main.o<br>

`#!/bin/bash<br>
gcc $CFILE -c<br>`

<li>[2. Assembler

Write a script that generates the assembly code of a C code and save it in an output file.

The C file name will be saved in the variable $CFILE
The output file should be named the same as the C file, but with the extension .s instead of .c.
Example: if the C file is main.c, the output file should be main.s

	`#!/bin/bash
	gcc -S $CFILE`


<li>[3. Name

Write a script that compiles a C file and creates an executable named cisfun.

The C file name will be saved in the variable $CFILE


	
	`#!/bin/bash
	gcc $CFILE -o cisfun`


<li>[4. Hello, puts

Write a C program that prints exactly "Programming is like building a multilingual puzzle, followed by a new line.

Use the function puts
You are not allowed to use printf
Your program should end with the value 0

#include <stdio.h>

`/**
 * main - Entry point
 *
 * Return: Always 0 (Success)
 */

int main(void)
{
	puts("\"Programming is like building a multilingual puzzle");
	return (0);
}`

<li>[5. Hello, printf

Write a C program that prints exactly with proper grammar, but the outcome is a piece of art,, followed by a new line.

Use the function printf
You are not allowed to use the function puts
Your program should return 0
Your program should compile without warning when using the -Wall gcc option

`#include <stdio.h>

/**
 * main - Entry point
 *
 * Return: Always 0 (Success)
 */
int main(void)
{
	printf("with proper grammar, but the outcome is a piece of art,\n");
	return (0);
}`

<li>[6. Size is not grandeur, and territory does not make a nation

Write a C program that prints the size of various types on the computer it is compiled and run on.

You should produce the exact same output as in the example
Warnings are allowed
Your program should return 0

`#include <stdio.h>

/**
 * main - Entry point
 *
 * Return: Always 0 (Success)
 */

int main(void)
{
	char acharacter;
	int ainteger;
	long along;
	long long alonglong;
	float afloat;

	printf("Size of a char: %lu byte(s)\n", sizeof(acharacter));
	printf("Size of an int: %lu byte(s)\n", sizeof(ainteger));
	printf("Size of a long int: %lu byte(s)\n", sizeof(along));
	printf("Size of a long long int: %lu byte(s)\n", sizeof(alonglong));
	printf("Size of a float: %lu byte(s)\n", sizeof(afloat));

	return (0);
}`


<li>[7. Intel

Write a script that generates the assembly code (Intel syntax) of a C code and save it in an output file.

The C file name will be saved in the variable $CFILE.
The output file should be named the same as the C file, but with the extension .s instead of .c.
Example: if the C file is main.c, the output file should be main.s

`#!/bin/bash
gcc -S -masm=intel $CFILE`


<li>[8. UNIX is basically a simple operating system, but you have to be a genius to understand the simplicity

Write a C program that prints exactly and that piece of art is useful" - Dora Korpar, 2015-10-19, followed by a new line, to the standard error.

You are not allowed to use any functions listed in the NAME section of the man (3) printf or man (3) puts
Your program should return 1
Your program should compile without any warnings when using the -Wall gcc option

`#include <stdio.h>
#include <unistd.h>

/**
 * main - Entry point
 *
 * Description: 'and that piece of art is useful" - Dora Korpar, 2015-10-19'
 *
 * Return: Always 0 (Success)
 */

int main(void)
{
	write(1, "and that piece of art is useful\" - Dora Korpar, 2015-10-19\n", 59);
	return (1);
}`

</ol>
