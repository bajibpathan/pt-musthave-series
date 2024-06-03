## Linux File System

In Linux everything is considered to be a file.
Directories (folders) are used to help you organize your files.

By having solid understing of Linux File System, you'll

- Enhance your Linux Skills
- Saves time in navgiation
- Improves your troubleshooting skills
- Understand location of different Linux components

The Linux file system is organized hierarchically, with the root directory serving as the starting point for all other directories

| Directory | Purpose                                                                                             |
| --------- | --------------------------------------------------------------------------------------------------- |
| /         | Top-level directory and serves as the starting point for navigating the file system                 |
| /bin      | Contains binaries and executable programs                                                           |
| /dev      | Contains device files or special files for devices that are attached to the system                  |
| /etc      | Stores system configuration files                                                                   |
| /home     | Contains user-specific files and directories                                                        |
| /media    | Directory for the system mounts removable media such as USB drives.                                 |
| /opt      | Reserved for add-on packages and third-party software applications that are not included by default |
| /usr      | Contains user related programs                                                                      |
| /tmp      | Directory that stores temporary files                                                               |
| /var      | Stores system-generated variable files, which include log files etc                                 |

### Shell

- Command-line interpreters that allow users to interact with the operating system
- Default shell program is **bash**

### Terminal

- A program called a “terminal emulator”
- Allows you interact with the shell

### Linux Commands

Command is a text-based instruction to perform a specific task or operation on a Linux system

### Type of Commands

- Executable Program
- Shell builtins
- Shell function
- Alias

### Command Structure

```bash
$ command options arguments
```

### Essential Commands

1. **type** - To identify the type of command

```bash
# Syntax:
$ type command

# Example:
$ type type
$ type ls
$ type cp
```

2. **which** - To determine the exact location of a given executable

```bash
# Syntax:
$ which exectuable

# Example:
$ which ls
```

3. **help** - To search for the documentation available for each kind of command

```bash
# Syntax:
$ help [options] command

# Example:
$ help -m cd
```

4. **--help** - To search for the documentation available for each kind of command

```bash
# Syntax:
$ command --help

# Example:
$ mkdir --help
```

5. **man** - To search for the documentation of the command in man pages

```bash
# Syntax:
$ man command

# Example:
$ man cp
```

6. **echo** - To prints out its text arguments on standard output

```bash
# Syntax:
$ echo agruments

# Example:
$ echo this is an example
```

7. **clear** - To clear the screen

```bash
# Syntax:
$ clear

# Example:
$ clear
```

8. **history** - To view the history of the commands typed

```bash
# Syntax:
$ history

# Example:
$ history
```

### Path

A path is how you refer to files and directories. It gives the location of a file or directory in the Linux directory structure. It is composed of a name and slash syntax.

Example:

```bash
$ /home/username/script/monitoring.sh
```

You'll have to use the path when you want to access a certain file or directory or when you have to give the location of a file or directory to a command.

If the path starts with slash "/", the first slash denotes root. The rest of the slashes in the path are just separators.

### Absolute Path

The Absolute path always starts from the root directory (/).

### Relative Path

A relative pathname starts from the working directory.

To do this, it uses a couple of special notations to represent relative positions in the file system tree. These special notations are "." (dot) and ".." (dot dot).

- . ( single dot) denotes to the working directory itself
- .. (two dots) refers to the working directory's parent directory

9. **pwd** - To display the present working directory

```bash
#Syntax:
$ pwd

#Example:
$ pwd
```

10. **ls** - To list the files and directories

```bash
#Syntax:
$ ls [options] [pathname]

#Example:
#To list the files and directories in the current working directory
$ ls

#To list the files and directories in the given path
$ ls /home/username

#To list the files and directories in the long listing format
$ ls -l /home/username

#output:
-rw-rw-r-- 1 john users 10300 Jun 01 08:10 abc.txt

Permissions             : -rw-rw-r--
Number of links         : 1
Owner name:             : john
Group name:             : users
File Size (bytes)       : 10300
Last modification time  : June 01 08:10
File name               : abc.txt

Commonly used other options with ls command
- a : to show all files including hidden
- h : display the file size in human readable format
- r : display the files in the reverse order
- t : sort by time

$ ls -l -r -h -t -a
or
$ ls -lrtha
```

11. **cd** - To change the present working directory

```bash
#Syntax:
$ cd pathname

#Example:
$ cd /usr/bin

#To navigate to partent directory
$ cd ..

#To change the working directory to home directory
$ cd

#To change the working directory to the previous one
$ cd -
```

12. **mkdir** - To create a directory

```bash
#Syntax:
$ mkdir directoryname

#Example:
$ mkdir learn_linux
```

13. **rmdir** - To delete an empty directory

```bash
#Syntax:
$ rmdir directoryname

#Example:
$ rmdir learn_linux
```

Note: If the directory is not empty, the command fails.

14. **touch** - To create blank/empty files

```bash
#Syntax:
$ touch filename

#Example:
$ touch abc.txt
```

Note: if you use the command on the existing file, it will modify the timestamp of the file

15. **cp** - To copy the contents of a file to a new file

```bash
#Syntax:
$ cp <source_file> <target_file>

#Example:
$ cp file.txt file_copy.txt

# Copy source_directory recursively to destination. If destination exists, copy source_directory into destination, otherwise create destination with the contents of source_directory.
$ cp  -r source_directory destination
```

16. **mv** - To move the files from one location to another location / rename the file

```bash
#Syntax:
$ mv <source_file> path

#Example:
$ mv file.txt ~/Documents/

# Rename the file
$ mv file_txt new_file.txt
```

17. **rm** - To delete the file or directory

```bash
#Syntax:
$ rm <file name>

#Example:
$ rm file.txt

# To delete the directory use -r option
$ rm -r old_logs
```

### Wild Cards

These special characters allow you to select filenames based on patterns of characters.

- - Matches any characters
    ? - Matches any single character
    [characters] - Matches any character that is a member of the set characters.
    [!characters] - Matches any character that is not a member of the set characters

Examples:
| Pattern | Matches|
| --------- | --------- |
| _ | All filenames |
| g_ | All filenames that begin with the character "g" |
| b*.txt | All filenames that begin with the character "b" and end with the characters ".txt" |
| Data??? | Any filename that begins with the characters "Data" followed by exactly 3 more characters |
| [abc]* | Any filename that begins with "a" or "b" or "c" followed by any other characters |

### I/O Redirections

Input and output in the Linux environment is distributed across three streams. These streams are:

- standard input (stdin)
- standard output (stdout)
- standard error (stderr)

The streams are also numbered:

- stdin (0)
- stdout (1)
- stderr (2)

Standard input comes from the user’s keyboard.
Standard output and standard error are displayed on the user’s terminal as text

Linux includes redirection commands for each stream.These can be used to write standard output or standard error to a file.

Overwrite

```bash
- > : standard output
- < : standard input
- 2> : standard error
```

Append

```bash
- >> : standard output
- <<> : standard input
- 2>> : standard error
```

### Pipes

Pipes are used to redirect a stream from one program to another. When a program’s standard output is sent to another through a pipe, the first program’s output will be used as input to the second, rather than being printed to the terminal. Only the data returned by the second program will be displayed.

The Linux pipe is represented by a vertical bar: |

18. **cat** - To display the content of a file

```bash
#Syntax:
$ cat [options] <filename(s)>

#Example:
# To display the content of a file
$ cat file.txt

# To display the content of a multiple files
$ cat file.txt fil1.txt

# To redirect the content of a single file to another
$ cat file.txt > new_file.txt

# To redirect the multiple file contents to a single file.
$ cat file.txt > new_file.txt

# To display the content of file in reverse order
$ tac file.txt

# To append the content of a file to another
$ cat file.txt >> file1.txt

# To create a new file
$ cat > file1.txt
Press Crtrl + d after to end the command execution

# To show line numbering
$ cat -n file1.txt
```

19. **more** - To view text files in your terminal one screen page at a time

```bash
#Syntax:
$ more [options] <filename>

#Example:
$ more /etc/sudo.conf

# To display the first N lines of files
$ more -5 /etc/sudo.conf

# To use more with cat command
$ cat /etc/sudo.conf | more
```

20. **less** - To view text files in your terminal one screen page at a time

```bash
#Syntax:
$ less [options] <filename>

#Example:
$ less /etc/sudo.conf

# To display the first N lines of files
$ less -5 /etc/sudo.conf

# To use more with cat command
$ cat /etc/sudo.conf | less
```

21. **head** - To return the specified number of files from the top

```bash
#Syntax:
$ head [options] <filename>

#Note: By default, it will print the  first  10 lines of each FILE to standard output if no options specified

#Example:
$ head file1.txt

# To display the first N lines from a given file
$ head -n 5 /etc/sudo.conf

# To display the first N lines from multiple files
$ head -n 5 file1.txt file2.txt

```

22. **tail** - To return the specified number of files from the bottom

```bash
#Syntax:
$ tail [options] <filename>

#Note: By default, it will print the last 10 lines of each FILE to standard output if no options specified

#Example:
$ tail file1.txt

# To display the first N lines from the given file
$ tail -n 5 /etc/sudo.conf

# To display the first N lines from multiple files
$ tail -n 5 file1.txt file2.txt

# To see the real time updates
$ tail -f file.txt
```

23. **grep** - To search and match the text pattern in the files

```bash
#Syntax:
$ grep [option] patterns [file_name]

#Example
# To find the matching string in the file
$ grep "error" log.txt

# To ignore the case of the matching string
$ grep -i "error" log.txt

# To display the non matching lines
$ grep -v "success" log.txt

# To find the line numbers against matching input strring
$ grep -n "error" log.txt

# To find the pattern for all the files in the current directory
$ grep "error" *

# To find the pattern for all the files in the current directory and subsequent directories recursively
$ grep -R "error" *

# To display the N number of lines before a search pattern
$ grep -B 4 "error" log.txt

# To display the N number of lines after a search pattern
$ grep -A 4 "error" log.txt

# To display the file name containing the matched pattern,
$ grep -l name *.conf

# To count the  search pattern matches in the file
$ grep -c "error" log.txt

# grep can be used along with other commands using |
$ ls | grep -i name
```

24. **find** - To find things based on the conditions

```bash
#Syntax:
$ find path options patterns

#Example:
# To find a file by name in the current directory
$ find . -name file.txt

# To find a file by name in the home directory
$ find /home -name file.txt
$ find ~ -name file.txt

# To find a  file by name in the home directory by ignoring case
$ find /home -iname file.txt

# To find directories in the root directory with the given name
$ find / -type d -name test

# To find files in the root directory with the given name
$ find / -type f -name *.log

```

25. **clear** - To clear the terminal display

```bash
#Syntax:
$ clear

#Example
$ clear
```

26. **exit** - To exit from the terminal

```bash
#Syntax
$ exit

#Example
$ exit
```

### Other Important commands for Administrators

```bash
$ uname -a
$ useradd
$ usermod
$ userdel
$ chmod
$ chown
$ id
$ last
$ who
$ hostname
$ uname -a
$ uname -r
$ nestat -nultp
$ ip a
$ ping host
$ ps -ef

```
