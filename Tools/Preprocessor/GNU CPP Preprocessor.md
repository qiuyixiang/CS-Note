
This Notes Include Some Special Utilities In GNU CPP Preprocessor !
And It Also Include Some Macro Programming Aspect in C Programming Language !

Reference From : GNU CPP Reference (Manual)

Overview Of Content:
- [Options](#Options)
- [Macro](#Macro)


# Options

Options Tutorial:

> The Options below only apply to the GNU C Preprocessor

## General
This Table Include Some General Options In GNU CPP

| Options | Description            |
| ------- | ---------------------- |
| --help  | show help information  |
| -C      | Don't Discard Comments |


## Headers
This Table Below List The Include Headers-Related Options

| Options     | Description                                                             |
| ----------- | ----------------------------------------------------------------------- |
| -H          | Print the name of each header file used                                 |
| -I dir      | Specify Include Path                                                    |
| -iquote     | Specify Include Path                                                    |
| -isystem    | Specify Include Path                                                    |
| -idirafter  | Specify Include Path                                                    |
| -nostdinc   | Don't Search for Standard System Path for C Headers                     |
| -nostdinc++ | Do not search for header files in the C++ specific standard directories |

Include Search Path:
1. Search For the current file path
2. -iquote options are searched
3. -I options are searched
4. -isystem options are searched
5. Standard System Path is searched
6. -idirafter options are searched


## Macro
This Table Below List The Macro-Related Options

| Options              | Description                              |
| -------------------- | ---------------------------------------- |
| -D _name_<br>        | define a macro with default value 1      |
| -D _name=definition_ | define a macro with the value definition |
| -U _name_            | Cancel any previous definition of name   |

## Dependencies
These Command Used to generate dependencies rules for _GNU Make_

| Options    | Description                                                                       |
| ---------- | --------------------------------------------------------------------------------- |
| -M         | Instead of outputting the result of preprocessing, Generate a rule for _GNU make_ |
| -MF _file_ | When use -M Options Using this command Option to specify which file to write      |
| -MD        | Generate both the output of preprocessing file and dependency file for _GNU make_ |
| -MM        | Similar to -M Option But Don't Contain System Header File                         |

# Macro

## General Macro

This Table Describe Some General Purpose Macro

| Preprocessor Directives | Description                                                                      |
| ----------------------- | -------------------------------------------------------------------------------- |
| `#define`               | Used to define a macro                                                           |
| `#undef`                | Used to undefine a macro                                                         |
| `#include`              | Used to include a file in the source code program                                |
| `#ifdef`                | Used to include a section of code if a certain macro is defined by `#define`     |
| `#ifndef`               | Used to include a section of code if a certain macro is not defined by `#define` |
| `#if`                   | Check for the specified condition                                                |
| `#else`                 | Alternate code that executes when `#if` fails                                    |
| `#endif`                | Used to mark the end of `#if`, `#ifdef`, and `#ifndef`                           |

## Predefined Macro

The Table Describe Some Standard Pre-defined Macros

| Macro           | Descriptions                                                             |
| --------------- | ------------------------------------------------------------------------ |
| `__FILE__`      | the name of the current file (const char *)                              |
| `__LINE__`      | the number of the current line (int)                                     |
| `__DATE__`      | Current Date in String (const char *)                                    |
| `__TIME__`      | Current Time (Similar with `__DATE__`)                                   |
| `__STDC__`      | Display whether the compiler conform ISO/ANSI C Standard                 |
| `__cplusplus`   | This macro is defined when the C++ compiler is in use                    |
| `__ASSEMBLER__` | This macro is defined with value 1 when preprocessing assembly language. |
| `__func__`      | Display the name of the function                                         |


## Demos In Macro

### Template For Test Cases

This is a Test Template Only Implemented Using C Macro !
```c
#ifndef __QLIBCPP_TEST_MAIN__  
#define __QLIBCPP_TEST_MAIN__ 1  
  
/**  
 * This Header File Defined Some Interface For Test Cases */#include <cassert>  
  
#define __USING_QLIBCPP_TEST_MACRO__  1  
  
#if defined(__USING_QLIBCPP_TEST_MACRO__) && __USING_QLIBCPP_TEST_MACRO__ == 1  
#define MAXI_TEST_CASES 100  
    typedef void (*__test_func_ptr)();  
    static __test_func_ptr __test_cases_group[MAXI_TEST_CASES] { };  
    static unsigned long __test_counter = 0;  
#endif  
  
/// Test Macro  
#define EXPECT_EQUAL(_expr1, _expr2)    assert((_expr1) == (_expr2))  
#define EXPECT(_)                       assert(_)  
  
#define _MACRO_JOIN(_X, _Y) _X##_Y  
#define _MACRO_TO_STR(__) #__  
  
#define TEST_CASE(_)                                                \  
void _MACRO_JOIN(qlibcpp, _)();                                     \  
__attribute__((constructor)) void _MACRO_JOIN(constructor, _)(){    \  
    __test_cases_group[__test_counter++] =                          \  
    static_cast<__test_func_ptr>(&_MACRO_JOIN(qlibcpp, _));         \  
}                                                                   \  
void _MACRO_JOIN(qlibcpp, _)()  
  
#define RUN_ALL_TEST(){                                                     \  
   for (unsigned long __index = 0; __index != __test_counter; ++__index)    \  
        (*(__test_cases_group[__index]))();                                 \  
}  
#endif
```

> This Example Come From qlibc++ Test Cases Template