
This Note is about GNU GCC Compiler Toolchain

## Command

### General


### Warning

| Command  | Usage                                                                                       |
| -------- | ------------------------------------------------------------------------------------------- |
| -Wall    | Turn on most of warning messages                                                            |
| -Werror  | forces the compiler to treat all compiler warnings as errors                                |
| -Wextra  | This flag add a few more warnings which not included by -Wall                               |
| -Wshadow | Warn whenever a local variable or type declaration shadows another variable, parameter type |

And you can use -W prefix to enable warning message or -Wno to disable warning message.

| Argument                     | Usage                                               |
| ---------------------------- | --------------------------------------------------- |
| -Wno-unused-parameter        | Disable Warnings of unused parameter                |
| -Wno-unused-variable         | Disable Warnings of unused variable                 |
| -Wno-unused-but-set-variable | Disable Warnings of unused but already set variable |

### Debugger

The Debugger use one argument for debugger level
- Level 0 produces no debug information at all
- Level 1 produces minimal information
- Level 2 is the default debug level
- Level 3 includes extra information

| Command              | Usage                                                                                                     |
| -------------------- | --------------------------------------------------------------------------------------------------------- |
| -g                   | This flag requests the compiler to generate and embed debugging information in the executable             |
| -ggdb                | Produce debugging information for use by GDB.                                                             |
| -ggdblevel           | Request debugging information and also use level to specify how much information. The default level is 2. |
| -fsanitize=address   | This flag enables the AddressSanitizer program, which is a memory error detector                          |
| -fsanitize=undefined | This flag enables the UndefinedBehaviorSanitizer program                                                  |



### Optimization
Optimization Level from O0 - O3, from no-optimization to maximum optimization.

| Command | Usage                                                                                  |
| ------- | -------------------------------------------------------------------------------------- |
| -O0     | This will compile your code without optimizations                                      |
| -O3     | - This will enable the most aggressive optimizations, making your code run the fastest |
