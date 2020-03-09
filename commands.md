#Compiling C Programs

gcc is the GNU C Compiler. Below are several examples that show how to use gcc to compile C programs. 

##Compiling a simple program.

Lets say you have a file helloworld.c as follows :

#include<stdio.h>

int main (){
    printf("Hello, World!");
    return 0;
}

You can compile and run it from the unix prompt as follows :
* >> gcc helloworld.c*

This creates an executable called "a.out". You can run it by typing the following command at the prompt.
* >> ./a.out

a.out is the default name for an executable. Use the "-o" option to change the name :
	% gcc -o hello hello.c
creates an executable called "hello".
