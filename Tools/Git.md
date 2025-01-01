
Git is a version control system. This note is about how to use this version control system.
# Commands

## Setup

### config


| Command  | Usage                                                                             |
| -------- | --------------------------------------------------------------------------------- |
| --global | Specify that the configuration is for global environment not for local repository |


Here is the list for git configuration. And using `git help --config` to list all available configuration variables.

| Argument   | Usage      |
| ---------- | ---------- |
| user.name  | user name  |
| user.email | user email |


## Stage

### commit

| Command | Usage                                                                                                                     |
| ------- | ------------------------------------------------------------------------------------------------------------------------- |
| -a      | automatically stage files that have been modified and deleted, but new files you have not told Git about are not affected |
| -m MSG  | Use the given MSG as the commit message.                                                                                  |

### add
The `git add` command add the file or directory to the staging area.


### rm

### status
The `git statis` command display the current state of the working directory.

## Branching
Git commits are arranged into lists called _branches_. The most important branch is `main`. This is the default branch which is created whenever you initialize a new git repository.

### restore

### switch

## Remote


## Inspection

### log
The `git log` command reports all of the commits in your current history. It lists them in reverse order, so the most recent commit comes first.


| Command | Usage                             |
| ------- | --------------------------------- |
| -p      | show each commits with difference |

### diff
Show changes between different places.

| Command                  | Usage                                                                |
| ------------------------ | -------------------------------------------------------------------- |
| git diff                 | see the differences between staging area and  working directory      |
| git diff COMMIT          | see the difference between a named commit and your working directory |
| git diff COMMIT1 COMMIT2 | see the differences between the two named commits                    |



