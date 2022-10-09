---
title: "Command line bascis"
---

https://www.taniarascia.com/how-to-use-the-command-line-for-apple-macos-and-linux/

Change permissions to user execution:
`chmod u+x filename`


## Missing semester of your CS eduction, MIT 2020
https://missing.csail.mit.edu/

### 1. Course overview + the shell 
https://missing.csail.mit.edu/2020/course-shell/

`~` is short for _home_
Type `date` to print (display) the current date and time. 

`echo`... Print commands with arguments, e.g. `echo "Hello Silfa"` --> prints "Hello Silfa" on the screen.

`echo $PATH` --> Prints the directories the should should search for when given a command. 

We can find out which file is executed for a given program using the `which` command, e.g. `which echo` shows where the file for the echo command is located (in my case, it results in "shell built-in command").

#### Navigating the shell
Path directories are separated by `/` on Linux and macOS and `\` on Windows. 

A path that starts with `/` is called an _absolute_ path. Any other path is a _relative_ path (i.e. relative to the current working directory).

`pwd` ... print working directory

`cd` ... change directory 

`ls` ... shows list of current directory. With `-l`, list files in long format, i.e. with permissions.

`mv` ... move/rename a file

`cp` ... copy a file

`mkdir`... make a new directory

In a path, `.` refers to the current directory, and `..` to its parent directory. So `cd ..` moves you "downwards" a level of directories.

Most commands accept flags and options (i.e. flags with values) that start with `-` to modify their behaviour. 

`--help` or `-h` in addition to command name will print some help text, e.g. `ls --help`. 

File permissions: list with `ls -l`
![](Pasted%20image%2020221009103057.png)
d = "missing" is a directory.

First block of 3 characters: owner of the file; then users; then everyone else. So, `rwx` = read, write and execute (search) access; `r-x` = only read and execute access. 

If you want more information about a command's or program's arguments, inputs, outputs, or how it works in general, try the `man` (= manual) program, e.g. `man ls`. 

**In terminal, press q for quit!**

#### Connecting programs
Input stream < program > output stream

Usually the input and output streams are the terminal, but that can be rewired.

`echo hello > hello.txt` creates a text file containing the word _hello_. 

`cat hello.txt` prints the contents of the hello.txt file to the screen. `cat` concetenates and prints files (usually to the standard output, unless otherwise stated). 

`cat < hello.txt > hello2.txt` prints the content of the hello.txt file (input, `cat < hello.txt`) to the hello2.txt file (output; `> hello2.txt`). 

You can also use `>>` to append to a file. The pipe operator `|` lets you "chain" programs such that the output of one is the input of another:

#### Root user
Root user is above (almost) all access restrictions and can create, read, update and delete any file in the system. It's very easy to accidentally break something as the root user, so you will not usually log into your system as root user. Instead, you will be using the `sudo` command. It lets you do (`do`) something as superuser (`su`). _But make sure you double-check that you really want to do it that way!!_

When you get permission denied errors, it's usually because you need to do someting as root.

#### More commands

`touch` ... Change file access and modification times. If file does not exist, it is created with default permissions. 

`chmod` ... Change file modes or access control lists.

`curl` ... Enables data transfer over various network protocols, suchas ftp, http, https, pop3, etc. It communicates with a web or application server by specifying a relevant URL and the data that needs to be sent or received. `--head` fetches the header only. `--silent` Silent or quiet mode that won't show progress meter or error messages.

`date` ... Display or set date and time. If combined with `-r` and a filename, the date and time of the last modification of filename is returned.

##### Exercises
1. Check that you're running an appropriate shell: `echo $SHELL` --> `/bin/zsh`, so everything looks good. 
2. Create a new directory called "Missing Semester": `mkdir "Missing Semster"`
3. Use `touch` to create a new file called "semester": `touch semester`
4. Write the following (line by line) into the file semester: 
```
#!/bin/sh
curl --head --silent https://missing.csail.mit.edu
```
 Use single quotes for the first line!! # starts a comand in Bash, and ! has a special meaning, even with double quotes.
5. `echo '#!/bin/sh' > semester`
6. `'curl --head --silent https://missing.csail.mit.edu' > semester`
7. Try to execute the file, i.e. type the path to the script: `./semester`. Permission denied. Why? --> `ls -l` shows `-rw-r--r--@`, i.e. I don't have executing access. 
8. Run the command by explicitely starting the `sh` interpreter and giving it the file semester as the first argument: `sh semester`. 

Why does this work, but `./semester` didn't?
_sh is a command language interpreter that executes commands read from a command line string, the standard input, or a specified file. I already have permission to execute sh, so it can run the semester script without problems. On the other hand, I don't have rights to execute the semester script directly._

9. Use `chmod` to make it possible to run the command `./semester` rather than having to type `sh semester`.
Change the executing rights with `chmod +x semester.sh`. 

11. How does your shell know that the file is supposed to be interpreted using `sh`? 

_The purpose of the shebang (`#!`) line is to tell the operating system (or whatever process launches the interpreter) what to use as the interpreter. _

11. Use `|` and `>` to write the "last modified" date output by semester into a file called last-modified.txt. 
```
date -r semester > last modified.txt
cat last-modified.txt 
```















