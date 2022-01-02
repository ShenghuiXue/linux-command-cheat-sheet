# The basic linux commands cheat sheet

## Table of contents
* [Basic command structure](#basic-command-structure)
* [Important commands](#important-commands)
  * [manual command](#manual-command)
    * man
  * [navigation commands](#navigation-commands)
    * pwd
    * ls
    * cd
  * [creating files and folders](#creating-files-and-folders)
    * touch
    * mkdir
  * [deleting, copying, and moving](#deleting-copying-and-moving)
    * rm
    * mv
    * cp
  * [working with files](#working-with-files)
    * cat (tac, rev)
    * less
    * head and tail
    * wc
    * sort
    * nano
* [Useful commands](#useful-commands)
* [Nice to have commands](#nice-to-have-commands)
* [Shortcuts](#shortcuts)

# Basic command structure
```s
command -options arguments
```

### Important commands
[Back to TOC](#table-of-contents) 
#### Manual command
[Back to TOC](#table-of-contents) 
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
[Back to TOC](#table-of-contents) 
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
[Back to TOC](#table-of-contents) 
* touch
  * Change file timestamps (the original intended use of **touch** ^0^)
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
#### Deleting, copying, and moving
[Back to TOC](#table-of-contents) 
* rm
  * Remove files and directories from our machine
  * Remove files. The deleted file cannot be redo and **cannot be found from the trash can**.
    ```s
    rm <file_name>
    ```
  * Remove **empty** directories.
    ```s
    rm -d <empty_directories>
    rm --dir <empty_directories>
    rmdir <empty_directories>
    ```
  * Remove directories and their contents recursively.
    ```s
    rm -r <directories> // be careful when you run this command
    rm -R <directories> // be careful when you run this command
    rm -ri <directories> // remove the file and directories interatively
    ```
  * 
* mv
  * Move files and directories from one location to another location
    ```s
    mv <source> <destination> // destination directory is exist
    mv <source_1> <source_2> <destination> // destination directory is exist
    ```
  * Rename **a single** file or **a single** dirctory
    ```s
    mv <original_name> <new_name> 
    mv <original_dir_and_name> <new_dir_and_name> 
    ```
* cp
  * Copy files and directoris
    ```s
    cp <source> <destination>
    cp <file_name> <new_file_name>
    cp <source_1> <source_2> <destination_dir>
    cp -r <dir_name> <destination_dir> // use -r to copy directory recursively
    ```
#### Working with files
[Back to TOC](#table-of-contents) 
* cat
  * Concatenates and prints the contents of files to the terminal
    ```s
    cat <file_name>
    ```
  * Related (but less importand) commands
    * tac
      * Concatenates and prints the contents of files to the terminal in **reverse** order for each line
        ```s
        tac <file_name>
        ```
    * rev
      * Concatenates and prints the contents of files to the terminal and reverse all characters in each line
        ```s
        rev 
        rev <file_name>
        ```
* less
  * Display the content of the file, one page at a time. 
    ```s
    less <file_name>
    ```
  * When viewing a file using less, 
    * press `space` or `f` to go the the next page
    * press `b` to go back to the previous page
    * press `enter` or `Down arrow` to scroll by one line
    * type `/ followed by a pattern` to search
    * press `q` to quit
* head
  * Print a port of a file starting from beginning. By default, print the first 10 lines of a file.
    ```s
    head <file_name>
    head -n 5 <file_name> // set how many lines to print out
    head -n5 <file_name> // set how many lines to print out
    head --lines 5 <file_name> // set how many lines to print out
    head -5 <file_name> // set how many lines to print out
    ```
* tail
  * Print a port of a file from the end By default, print the last 10 lines of a file.
    ```s
    tail <file_name>
    tail -n 5 <file_name> // set how many lines to print out
    tail -n5 <file_name> // set how many lines to print out
    tail --lines 5 <file_name> // set how many lines to print out
    tail -5 <file_name> // set how many lines to print out
    ```
* wc
  * This command prints counts the number of lines, words, and characters in one or mutiple files 
    ```s
    wc <file_name>
    wc <file_name_1> <file_name_2>
    ```
  * Explain the output:
    ```s
    // output
    308  1703 10488 README.md
    // README.md file has 308 lines, 1703 words, and 10488 characters
    ```
  * Lines count
    ```s
    wc -l <file_names>
    ```
  * Words count
    ```s
    wc -w <file_names>
    ```
  * Characters count and bytes count
    ```s
    wc -m <file_names>
    wc -c <file_names>
    ```
* sort
  * Sort each lines in a given file
    ```s
    sort <file_name> // case insensitive, lower case come first
    sort -r <file_name> // sort with reverse order
    sort -n <file_name_with_numbers> // sort by comparing the numeric values in each line
    sort -u <file_name> // sort and only keep uqiue values
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
  * We can use nano to **create a new file** as well. We can type nano and follow a file name that does not exists.
    ```s
    nano <file_name_that_to_be_created>
    ```
### Useful commands
[Back to TOC](#table-of-contents) 
* clear
  * Clear the terminal
* file
  * Show the type of the file (or the folder)
    ```s
    file <file_name or folder_name>
    ```
* history
  * Display all the command lines you entered previously
    ```s
    history
    history | less
    ```
  * You can rerun the history commands using "!+history_id"
    ```s
    history // this list the hisotry commands with id
    !7 // run the command of id 7 in the history
    ```
  * You can use "Ctrl + r" to search history
  * History commands are saved in "~/.bash_history", so you can find all the history commands using `nano ~/.bash_history`.
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
  * Open a specific folder in the gui of ubuntu
    ```s
    xdg-open <folder_dir>
    ```
  * Open a specific folder in the gui of mac
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
[Back to TOC](#table-of-contents) 
* date
  * Print out the time of the system
* ncal 
  * Print out a vertical calander of current month
  * Print out the calendar of the entire year: 
    ```s
    ncal 2025
    ```
  * Print out the calendar of a given month in a given year
    ```s
    ncal jan 2022
    ```
### Shortcuts
[Back to TOC](#table-of-contents)
* **Ctrl + a**: jump the cursor at the begin of the line.
* **Ctrl + e**: jump the cursor at the end of the line.
* **Ctrl + f**: move the cursor forward for one character.
* **Ctrl + b**: move the cursor backward for one character.
* **Alt + f**: move the cursor forward for one word.
* **Alt + b**: move the cursor backward for one word.
* **Crtl + l**: clear console by moving view part up.
* **Ctrl + t**: swap two characters next to each other.
* **Alt + t**: swap two words next to each other.
* **Ctrl + k**: kill the text from the current cursor to the end of the line.
* **Ctrl + u**: kill the text from the current cursor to the beginning of the line.
* **Alt + d**: kill the text from the current cursor to the end of the word.
* **Ctrl + d**: kill the charactor in the current cursor.