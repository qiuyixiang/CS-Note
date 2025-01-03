

## Variables

Here is a list of common automatic variables
- `$@` represents the name of the current rule’s target.  
- `$^` represents the names of all of the current rule’s dependencies, with spaces in between.  
- `$<` represents the name of the current rule’s first dependency.

## Functions

### utility


| Function         | Usage                                    |
| ---------------- | ---------------------------------------- |
| $(shell COMMAND) | Execute the COMMAND In Shell Environment |
| $(sort LISTS)    | Sort the LISTS in dictionary order       |

### String

| Function                    | Usage                                                          |
| --------------------------- | -------------------------------------------------------------- |
| $(dir NAMES...)             | Extracts the directory-part of each file name in NAMES         |
| $(notdir NAMES…)            | Extracts all but the directory-part of each file name in NAMES |
| $(basename NAMES…)          | Extracts all but the suffix of each file name in NAMES         |
| $(addsuffix SUFFIX, NAMES…) | Add SUFFIX to every NAMES                                      |
| $(addprefix PREFIX, NAMES…) | Add PREFIX to every NAMES                                      |
| $(patsubst FROM, TO, LISTS) | Pattern Substitute from FROM to TO using elements in LISTS     |
