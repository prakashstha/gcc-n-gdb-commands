# Compiling C Programs

gcc is the GNU C Compiler. Below are several examples that show how to use gcc to compile C programs. 

### Compiling a Simple C Program.

Lets say you have a file helloworld.c as follows :

> #include<stdio.h>
int main (){
    &nbsp; &nbsp; printf("Hello, World!");
    &nbsp; &nbsp; return 0;
}

You can compile and run it from the unix prompt as follows :
> gcc helloworld.c*

This creates an executable called "a.out". You can run it by typing the following command at the prompt.
> ./a.out

a.out is the default name for an executable. Use the "-o" option to change the name. The followind command creates an executable called "helloworld".
> gcc  helloworld.c -o helloworld

### Including Directories

The header files that you include using *"#include"* may not be in the same directory as you *.c* file. Say you have *helper.h* file in */homes/username/include*. You need to run the C program using following command.
-   add following statement to *helloworld.c* 
    > #include < helper.h >
-   compile with the -I option :
    > gcc -I /homes/username/include helloworld.c -o helloworld
    
This tells gcc to look for #include files in */homes/username/include **in addition** to other directories you specify with -I

### Other Options
- Wall: Turns on most warnings
- Werror: Make all warnings into errors.

### Compiling multiple files
*Basic Idea* is to compile each *.c* file into a *.o* file, then compile the *.o* files (along with any libraries) into an executable. One of these *.c* files obviously has to define the main function.

Suppose we have *driver_program.c*, *helper_1.c* and *helper_2.c* and want to create an executable *driver* file. Further, let say we need the math library.
> gcc -c helper_1.c
> gcc -c helper_2.c
> gcc -c driver_program.c
> gcc -o driver helper_1.o helper_2.o driver_program.o -lm

The first three commands generate *helper_1.o, helper_2.o* and *driver_program.o*, respectively. The last line links them together along with the math library.

### Libraries
To include libray, you can use -L option. 
e.g., 
> -L /usr/lib. 
 
This tells gcc to look for libraries in /usr/lib. 
