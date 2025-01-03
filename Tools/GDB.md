
This Note is about GNU Debugger Tool GDB.

##  Command

### layout

layout is a build-in command to control the layout of the code

| Argument | Usage                        |
| -------- | ---------------------------- |
| asm      | Apply the Assembly layout    |
| next     | Apply the next layout        |
| prev     | Apply the previous layout    |
| regs     | Apply the  registers layout  |
| split    | Apply the split layout       |
| src      | Apply the Source File layout |



### breakpoints

Breakpoints are used in gdb to stop a program whenever a certain point in the program is reached. You can set breakpoints at a function, at a specific line within the file you are currently running, or even at a line within another file. 

Using command `break` or `b` to set a break point.


| Argument          | Usage                                       |
| ----------------- | ------------------------------------------- |
| [b]reak  FUNC     | set breakpoint at a specific function       |
| [b]reak LINE      | set breakpoint at line LINE within the file |
| [b]reak FILE:LINE | set breakpoint at file FILE, line LINE      |



### information

`info`(`i`) is a command to display debugger information


| Argument             | Usage                                                              |
| -------------------- | ------------------------------------------------------------------ |
| [i]nfo checkpoints   | Display current breakpoints                                        |
| [i]nfo all-registers | List of all registers and their contents, for selected stack frame |


### delete

delete is a command used to delete some argument or attribute which be settled.


| Argument       | Usage                        |
| -------------- | ---------------------------- |
| [d]elete       | Delete all breakpoints       |
| [d]elete BREAK | Delete breakpoint with BREAK |


### execution
To commence execution, you can use the command run followed by any arguments that might be required to run the program.

| Argument   | Usage                                                |
| ---------- | ---------------------------------------------------- |
| [r]un      | run the program without argument                     |
| [r]un ARG  | run the program with ARG                             |
| [c]ontinue | continue to the next breakpoint                      |
| [n]ext     | continue to the next line, steps over function calls |
| [s]tep     | continue to the next line, steps into function calls |
| [q]uit     | quits GDB                                            |
|            |                                                      |
