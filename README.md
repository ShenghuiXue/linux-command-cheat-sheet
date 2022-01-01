# The basic linux commands cheat sheet

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
    man -k <command_name>
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
    ls <folder_dir>
    ls ~
    ```
  * List the contents of a directory with long format
    ```s
    ls -l
    ls -l <folder_dir>
    ```
  * List all the contents of a directory including hiding fils and folders
    ```s
    ls -a
    ls -a <folder_dir>
    ```
  * List **all** the contents of a directory with **long** format
    ```s
    ls -la
    ls -la <folder_dir>
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
* touch
  * Change file timestamps (the original intended user of **touch** ^0^)
  * Create a **new** file or mutiple **new** files **if not exist**
    ```s
    touch <file_path_and_file_name>
    touch <file_name_1> <file_name_2> // creating multiple files in the current directory
    ```
  * You can create a new file in a specified directory as well:
    ```s
    touch ~/abc.txt  // create a new file named abc.txt in the HOME directory
    ```
* mkdir
  * Create new directories
    ```s
    mkdir <file_name>
    mkdir <file_name_1> <file_name_2>
    mkdir <file_path_and_file_name>
    ```
  * If you want to make mutiple nested directoris, you can use ***-p*** option.
    ```s
    // this command will show ERROR if animals or cats directory is not available
    mkdir animals/cats/small_cats

    // this command will create all three directories even if 
    // animals and cats directories are not available
    mkdir -p animals/cats/small_cats 
    ```

### Useful commands
* clear
  * Clear the terminal
* file
  * Show the type of the file (or the folder)
    ```s
    file <file_name or folder_name>
    ```
* nano
  * nano is a program that we can use to open and edit files from the commandline
    ```s
    nano <file_path_and_file_name>
    ```
  * short cuts:
    * Shortcuts are written as follows: **Control-key** sequences are notated with a **'^'** and can be entered either by using the Ctrl key or pressing the Esc key twice.  **Meta-key** sequences are notated with **'M-'** and can be entered using either the **Alt, Cmd, or Esc** key, depending on your keyboard setup.
    * **Crtl + o (^O)**: write out the file and the nano will ask which file will be write to
    * **Ctrl + x**: exit/close
    * **Ctrl + s**: save the file changes
    * **Ctrl + c**: cancel
    * **Ctrl + g**: go to help manual
    * **Ctrl + w**: serach
    * **Ctrl + \\**: serach and replace
    * **Ctrl + t**: use spell checker
      * spell check is disabled by default. 
      * we can enable the spell check by editing the configration file located at `/etc/nanorc` using `sodu nano /etc/nanorc`
    * **Alt + u (M-U)**: undo
    * **Alt + e**: redo
    * **Alt + s**: Soft wrapping of overlong lines enable/disable
  * we can use nano to **create a new file** as well. We can type nano and follow a file name that does not exists.
    ```s
    nano <file_name_that_to_be_created>
    ```
* sort
  * Sort each lines in a give file
    ```s
    sort <file_name>
    ```
* type
  * Tells the types of command
    ```s
    type <command_name>
    ```
  * There are four types of commands:
    * An executable program which usually sotred in /bin, /usr/bin, or /usr/local/bin. These are comipled binary files (hence bin)
    * A built-in shell command. These commands are part of the shell, such as bash and zsh.
    * A shell function.
    * An alias.
* xdg-open, open
  * open a specific folder in the gui of ubuntu
    ```s
    xdg-open <folder_dir>
    ```
  * open a specific folder in the gui of mac
    ```s
    open <folder_dir>
    ```
* which
  * Tells where is the command is located.
  * Related commands: ***type***, ***man***
    ```s
    which command_name
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
