# Debugging a C Program

gdb is "GNU Debugger" for several programming languages including C and C++.

Use -g option while compiling to enable built-in debugging support that *gdb* needs. 

Say you have a *factorial.c* program as below. 
>#include <stdio.h>

>int main(){

> &nbsp;&nbsp; int i, j, num

> &nbsp;&nbsp; for (i = 1: i<num; i++){

> &nbsp;&nbsp;&nbsp;&nbsp; j = j*i

>&nbsp;&nbsp; printf("The factorial of %d is %d: ", num, j)

>}

Compile using the command below. 
> gcc -g factorial.c -o factorial

To start *gdb* with *helloworld* program use the following command, it will prompt *(gdb)*
> gdb factorial

Or, you can simply run *gdb*, then use the following command to load the *helloworld* program. 

Use the *help* command to get information about different commands in *gdb*
> ( gdb ) help

Use the *run* command to run the program
> (gdb) run

Breakpoints are used to stop the program run at a specified point.
> (gdb) break 4
or 
> (gdb) break factorial.c:4
This sets a breakpoint at a line number 4 in the *factorial.c*.

You can also set a break point at a function
> (gdb) break funcation_name

Once breakpoints are set, use the *run* command to execute the program. The program will stop at the first set breakpoint.

Use *continue* command to continue to the next breakpoint. If you use *run* command again, it will restart the program from the beginning.

Use *next* command to execute the next statement in the program. The *next* command does not jump the control to the sub-routing. In order to jump the control to the sub-routine, use *step* command instead.
> (gdb) next

Use *print* or *p* command to print the value in the specified variable
> (gdb) print num
or
> (gdb) p num

Use *watch* command to pause the program when watched variable's value is modified.
> (gdb) watch num

Other commands
- **finish:** runs until the current function is finished.
- **delete** or **clear**:  remove specified break points.
- **info breakpoints**: shows information about all declared break points.  










