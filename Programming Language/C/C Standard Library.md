
# Introduction

C Standard Library

This Note Mainly Include Some Topics in C Standard Library.
Cover ISO/ANSI C Standard : c89, c99, c11

Reference TextBook : 
![](../../_IMG/PL/Snipaste_2024-04-23_14-23-52.png)
Outsider Website : C Reference 

A Overview Of The Content :

- Diagnostic Library
- String Library
- Dynamic Memory Library
- Standard IO Library
- Type Library

Here is a List Of the Headers which will implement soon : 

The Headers which are included in C89
- <assert.h>
- <ctype.h>
- <errno.h>
- <float.h>
- <limits.h>
- <locale.h>
- <math.h>
- <setjmp.h>
- <signal.h>
- <stdarg.h>
- <stddef.h>
- <stdio.h>
- <stdlib.h>
- <string.h>
- <time.h>


# Diagnostic Library

Diagnostic Library For C Standard 
- [assert](#assert)

## assert

```c
assert(expr)
```
description:
	assert is a function-like Macro in C Standard. if the _expr_ is true it do nothing else it will abort the program and show error message ! You can use _NDEBUG_ to disable the assertion !

argument:
- expr : judge whether the argument is true

return:
	None


# String Library

This Library Include Single-Byte (Character) and Multi-Byte (String) Functions and Utilities.

## Character

All Of these Character Function Defined In <ctype.h>

| Function       | Description                                                             |
| -------------- | ----------------------------------------------------------------------- |
| isalnum(char)  | checks if a character is alphanumeric                                   |
| isalpha(char)  | checks if a character is alphabetic                                     |
| islower(char)  | checks if a character is a lower alphabetic character                   |
| isupper(char)  | checks if a character is a upper alphabetic character                   |
| isdigit(char)  | checks if a character is a digit                                        |
| isxdigit(char) | checks if a character is a hexadecimal character                        |
| iscntrl(char)  | checks if a character is a control character                            |
| isgraph(char)  | checks if a character is a graphical character (visible character)      |
| isspace(char)  | checks if a character is a space character (\\n, \\t)                   |
| isblank(char)  | checks if a character is a blank character (\\0, \\t)                   |
| isprint(char)  | checks if a character is a printing character                           |
| ispunct(char)  | checks if a character is a punctuation (visible and non-zero character) |
| toupper(char)  | converts a character to uppercase                                       |
| tolower(char)  | converts a character to lowercase                                       |

ASCII Table

| Decimal | Hexidecimal   | ASCII                                |
| ------- | ------------- | ------------------------------------ |
| 0–8     | `\x0`–`\x8`   | control codes (`NUL`, etc.)          |
| 9       | `\x9`         | tab (`\t`)                           |
| 10-13   | `\xA`–`\xD`   | whitespaces (`\n`, `\v`, `\f`, `\r`) |
| 14–31   | `\xE`–`\x1F`  | control codes                        |
| 32      | `\x20`        | space                                |
| 33–47   | `\x21`–`\x2F` | `!"#$%&'()*+,-./`                    |
| 48–57   | `\x30`–`\x39` | `0123456789`                         |
| 58–64   | `\x3A`–`\x40` | `:;<=>?@`                            |
| 65–70   | `\x41`–`\x46` | `ABCDEF`                             |
| 71–90   | `\x47`–`\x5A` | `GHIJKLMNOP`  <br>`QRSTUVWXYZ`       |
| 91–96   | `\x5B`–`\x60` | `` [\]^_` ``                         |
| 97–102  | `\x61`–`\x66` | `abcdef`                             |
| 103–122 | `\x67`–`\x7A` | `ghijklmnop`  <br>`qrstuvwxyz`       |
| 123–126 | `\x7B`–`\x7E` | `{\|}~`                              |
| 127     | `\x7F`        | backspace character (`DEL`)          |

## String

## Wide-Character

# Dynamic Memory Library

# Standard IO Library


# Type Library

There are some different type support Library In C . Here Mainly Include <stddef.h>
There are different type define in <stddef.h>

> Some Type Define There , There are just Macros, this approach is useful when you want to implement a kernel and use a portable C Standard library !

- size_t  : unsigned integer type
- ptrdiff_t :  signed integer type
- wchar_t : unsigned char type the size of this type may be 2 or 4 according to the implementation and machine architecture
- NULL : which is a pointer type which means 0  _((void *)0)_

The Function-like Macro offsetof:
```C
offsetof(type, member)
```

description : 
	This is a function-like macro which used to return the offset of the _member_ in the struct type _type_. 

argument:
- type : the type of the structure
- member : the member of the structure

return:
	size_t, return the _size_t_ type which is the offset of the _member_ in _type_