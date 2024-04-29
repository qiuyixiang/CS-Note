This Note Mainly List Some Class or template Class In C++ and Some Utilities Functions In C++ ! Later In this Note it also display how to implement a C++ Standard template Library !

Overview of the Content !

- String Library
- IO Library


# String Library

In C++ String Library Mainly include std::basic_string and some other forms of String Operation. The Library is implemented using Template and Class !

## basic_string

The class template _basic_string_ stores and manipulates sequences of character-like objects.
### basic_string Data Type


### basic_string member function

Overview of the basic_string member function

> All of these functions are member function, these notes is condensed and ignored the template and specialization traits !

| Member Function             | Descriptions                                                                                                                  |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| append(str)                 | add text to the end of a string                                                                                               |
| compare(str)                | return -1, 0, or 1 depending on relative ordering                                                                             |
| erase(index,length)         | delete text from a string starting at given index                                                                             |
| find(str)  <br>rfind(str)   | return first or last index where the start of str appears in this string (returns _string::npos_ if not found)                |
| insert(index, str)          | add text into string at a given index                                                                                         |
| length()                    | return number of characters in the string                                                                                     |
| replace(index,len,str)      | replace len chars at given index with new text                                                                                |
| substr(start, length)  <br> | return a new string with the next length chars beginning at start (inclusive); if length is omitted, grabs till end of string |
| size()                      | return number of characters in the string                                                                                     |


# IO Library

IO Library In C++ is divided into three different parts:
- Stream Based IO
- Print Based IO
- C-Style Based IO

The Most Important one is Stream Based IO Library

> the Print Based IO Start at ISO C++ 23

## Stream Based IO

### IO Hierarchy
The stream-based input/output library is organized around abstract input/output devices. These abstract devices allow the same code to handle input/output to files, memory streams, or custom adaptor devices that perform arbitrary operations on the fly.

IO Hierarchy :
![](../../_IMG/PL/Snipaste_2024-04-29_16-13-33.png)


## IO Manipulators

IO Manipulators are manipulators which control the output/input format of the Stream.

