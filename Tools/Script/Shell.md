
Shell is a powerful command tools, most Operating System provide System Interface through this command tools.

This Note is all about shells in different Operating System.
Copyright: @QiuYiXiang

---------------
reference University Course:
- MIT Missing Semester Of Your CS Education


Overview of the content : 
- [Command](#Command)
- [Script](#Script)


# Command

Overview of the Shell Command Application and some build-in Tools !
- [date](#date)
- [echo](#echo)
- [cat](#cat)
- [ls](#ls)
- [tail](#tail)
- [curl](#curl)
- [grep](#grep)

You can find where shell find these programs of build-in command using a environment variable _$PATH_
```shell
echo $PATH
```

Pipe Command
Using Pipe, you can put the output of the first command as the input of the second command!
```shell
command1 | command2
```

Output/Input Command
Using Output/Input Commands, you can read or write from/to a file from a command !
```shell
command >> file
command < file
```

> Note : 

the difference with `>` or `>>` 
- the `|` command need both of the operand are command
- the `>` or `>>` needs one side can be a command but the other side will be a file to be written

## date

_date_ display current time and date
```shell
~$ date
Sun May  5 17:15:18 CST 2024
```

## echo
_echo_ is a shell build-in command, using this command you can print some information.

```shell
echo "Hello World"
```

## cat
_cat_ concatenate and print files

```shell
cat data.txt
```

Flags for _cat_:

| Flags | Description                                                                                                  |
| ----- | ------------------------------------------------------------------------------------------------------------ |
| -b    | Number the non-blank output lines, starting at 1.                                                            |
| -e    | Display non-printing characters (see the -v option), and display a dollar sign (‘$’) at the end of each line |
| -n    | Number the output lines, starting at 1                                                                       |

## ls
_ls_ list directory contents. 
Unless a directory is given as its first argument, `ls` will print the contents of the current directory by default. Most commands accept flags and options (flags with values) that start with `-` to modify their behavior

General Usage:
```shell
ls  ./dir -a -l
```

Examples of Display Format for _-l_:
```shell
drwxr-xr-x   5 qiuyixiang  staff    160 Apr 26 10:52 Coding
```

- d means it is a directory
- the first rwx means the permission for the owner
- the second r-x means the permission for the owner group
- the third r-x means the permission for everyone

Flags for _ls_:

| Flags | Description                                                   |
| ----- | ------------------------------------------------------------- |
| -a    | Include directory entries whose names begin with a dot (‘.’). |
| -l    | List files in the long format, a more detailed display        |
 
## tail

tail list the last part of the file

```shell
// To display the last 500 lines of the file foo:
$ tail -n 500 foo
```

Flags for _tail_

| Flags | Description                           |
| ----- | ------------------------------------- |
| -n    | the line number which want to display |


## curl
curl is a tool for transferring data from or to a server using URLs

```shell
curl --head --silent baidu.com
```


## grep

The grep utility searches any given input files, selecting lines that match one or more patterns
```shell
grep pattern file
```
# Script