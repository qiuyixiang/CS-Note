
This Note is about GNU GCC Compiler Toolchain

## Command

### General


### Warning

| Command | Usage                                                         |
| ------- | ------------------------------------------------------------- |
| -Wall   | Turn on most of warning messages                              |
| -Werror | forces the compiler to treat all compiler warnings as errors  |
| -Wextra | This flag add a few more warnings which not included by -Wall |
|         |                                                               |


### Debugger

| Command              | Usage                                                                                         |
| -------------------- | --------------------------------------------------------------------------------------------- |
| -g                   | This flag requests the compiler to generate and embed debugging information in the executable |
| -fsanitize=address   | This flag enables the AddressSanitizer program, which is a memory error detector              |
| -fsanitize=undefined | This flag enables the UndefinedBehaviorSanitizer program                                      |


### Optimization
Optimization Level from O0 - O3, from no-optimization to maximum optimization.

| Command | Usage                                                                                  |
| ------- | -------------------------------------------------------------------------------------- |
| -O0     | This will compile your code without optimizations                                      |
| -O3     | - This will enable the most aggressive optimizations, making your code run the fastest |
