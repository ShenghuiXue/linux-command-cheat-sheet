# Linux commands cheat sheet

## Table of content
* [Basic command structure](#basic-command-structure)
* [Important commands](#important-commands)
* [Useful commands](#useful-commands)
* [Nice to have commands](#nice-to-have-commands)

# Basic command structure
```s
command -options arguments
```

### Important commands
#### Manual command
* man
  * Read the manual page of a command
    ```s
    man ncal
    ```
  * Search a command
    ```s
    man -k command_name
    man -k passwd
    ```
  * Read the mannual page of a command in a specific session
    ```s
    man 1 passwd
    ```
  * Not all commands have commands entries. Some commands that are build in shell do not have manual information and you can use ***help*** command. 
    ```s
    help cd
    ```
#### Navigation commands
* pwd
  * Print the working directory
* ls
  * List the contents of a directory
  * List the contents of the current working directory:
    ```s
    ls
    ```
  * List the contents of a specific folder
    ```s
    ls folder_dir
    ls ~
    ```
  * List the contents of a directory with long format
    ```s
    ls -l
    ls -l folder_dir
    ```
  * List all the contents of a directory including hiding fils and folders
    ```s
    ls -a
    ls -a folder_dir
    ```
  * List **all** the contents of a directory with **long** format
    ```s
    ls -la
    ls -la folder_dir
    ```
  * List **all** the contents of a directory with **long** **human-readable** format
    ```s
    ls -lah
    ```
  * Lists the contents of a directory and **sorted** by size
    ```s
    ls -s
    ls --sort=time     // sort by time
    ```
* cd
  * Change the directory
    ```s
    cd folder_dir
    cd ..  // go to the parent directory
    cd ~   // go to user HOME directory
    cd /   // go to the root directory
    cd -   // go to the previous directory
    ```
  * **A single dot (.)**: the reference to the current diretory
  * **Double dots (..)**: are the reference to the parent directory
  * **/**: the root directory
  * **~**: the user HOME directory
  * Overview of the directories in linux:
    * **/bin**: "bin" is short for "binary directory". This directory contains lots of exectable programs.
    * **/etc**: contains configration (setting) files and initialization scripts.
    * **/media**: accesses the contents of the removable media, such as usb drive and sd card.
    * **/var**: "var" is short for "varaible". This directory contains files related with logging, the outputs from other programs, and caches.
    * **/root**: is the home directory of the super user (root user), which is different from "/".
    * **/usr**: contains exectable files, libraies. If you install a software, it will be most likely in this folder.

#### Creating files and folders

### Useful commands
* clear
  * Clear the terminal
* which
  * Tells where is the command is located.
  * Related commands: ***type***, ***man***
    ```s
    which command_name
    ```
* sort
  * Sort each lines in a give file
    ```s
    sort file_name
    ```
* type
  * Tells the types of command
    ```s
    type command_name
    ```
  * There are four types of commands:
    * An executable program which usually sotred in /bin, /usr/bin, or /usr/local/bin. These are comipled binary files (hence bin)
    * A built-in shell command. These commands are part of the shell, such as bash and zsh.
    * A shell function.
    * An alias.
* xdg-open, open
  * open a specific folder in the gui of ubuntu
    ```s
    xdg-open folder_dir
    ```
  * open a specific folder in the gui of mac
    ```s
    open folder_dir
    ```

### Nice to have commands
* date
  * print out the time of the system
* ncal 
  * print out a vertical calander of current month
  * print out the calendar of the entire year: 
    ```s
    ncal 2025
    ```
  * print out the calendar of a given month in a given year
    ```s
    ncal jan 2022
    ```
