# The basic linux commands cheat sheet
This cheat sheet created based on the Udemy online course by Colt Steele: [The Linux Command Line Bootcamp: Beginner To Power User](https://www.udemy.com/course/the-linux-command-line-bootcamp/).

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
  * [Redirection](#redirection)
    * \>: redirect standard output
    * \>>: append standard output
    * 2>: redirect standard error
    * 2>>: append standard error
    * <: redirect standard input
  * [Piping](#piping)
    * |
    * tee
  * [Finding things](#finding-things)
    * locate
    * find
* [Useful commands](#useful-commands)
* [Nice to have commands](#nice-to-have-commands)
* [Shortcuts](#shortcuts)
* [Expansion](#expansion)
  * pathname expansion
  * tilde expansion
  * brace expansion
  * arithmetic expansion
  * single and double quotes
  * command substitution

## Basic command structure
```s
command -options arguments
```

## Important commands
[Back to TOC](#table-of-contents) 
### Manual command
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
  * Read the manual page of a command in a specific session
    ```s
    man 1 passwd
    ```
  * Not all commands have commands entries. Some commands that are build in shell do not have manual information and you can use ***help*** command. 
    ```s
    help cd
    ```
### Navigation commands
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
  * **A single dot (.)**: the reference to the current directory
  * **Double dots (..)**: are the reference to the parent directory
  * **/**: the root directory
  * **~**: the user HOME directory
  * Overview of the directories in linux:
    * **/bin**: "bin" is short for "binary directory". This directory contains lots of executable programs.
    * **/etc**: contains configuration (setting) files and initialization scripts.
    * **/media**: accesses the contents of the removable media, such as usb drive and sd card.
    * **/var**: "var" is short for "variable". This directory contains files related with logging, the outputs from other programs, and caches.
    * **/root**: is the home directory of the super user (root user), which is different from "/".
    * **/usr**: contains executable files, libraries. If you install a software, it will be most likely in this folder.

### Creating files and folders
[Back to TOC](#table-of-contents) 
* touch
  * Change file timestamps (the original intended use of **touch** ^0^)
  * Create a **new** file or multiple **new** files **if not exist**
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
  * If you want to make multiple nested directories, you can use ***-p*** option.
    ```s
    // this command will show ERROR if animals or cats directory is not available
    mkdir animals/cats/small_cats

    // this command will create all three directories even if 
    // animals and cats directories are not available
    mkdir -p animals/cats/small_cats 
    ```
### Deleting, copying, and moving
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
    rm -ri <directories> // remove the file and directories interactively
    ```
  * 
* mv
  * Move files and directories from one location to another location
    ```s
    mv <source> <destination> // destination directory is exist
    mv <source_1> <source_2> <destination> // destination directory is exist
    ```
  * Rename **a single** file or **a single** directory
    ```s
    mv <original_name> <new_name> 
    mv <original_dir_and_name> <new_dir_and_name> 
    ```
* cp
  * Copy files and directories
    ```s
    cp <source> <destination>
    cp <file_name> <new_file_name>
    cp <source_1> <source_2> <destination_dir>
    cp -r <dir_name> <destination_dir> // use -r to copy directory recursively
    ```
### Working with files
[Back to TOC](#table-of-contents) 
* cat
  * Concatenates and prints the contents of files to the terminal
    ```s
    cat <file_name>
    ```
  * Related (but less important) commands
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
  * This command prints counts the number of lines, words, and characters in one or multiple files 
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
    sort -u <file_name> // sort and only keep unique values
    ```
* nano
  * nano is a program that we can use to open and edit files from the command line
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
    * **Ctrl + w**: search
    * **Ctrl + \\**: search and replace
    * **Ctrl + t**: use spell checker
      * spell check is disabled by default. 
      * we can enable the spell check by editing the configuration file located at `/etc/nanorc` using `sudo nano /etc/nanorc`
    * **Alt + u (M-U)**: undo
    * **Alt + e**: redo
    * **Alt + s**: Soft wrapping of overlong lines enable/disable
  * We can use nano to **create a new file** as well. We can type nano and follow a file name that does not exists.
    ```s
    nano <file_name_that_to_be_created>
    ```
### Redirection
[Back to TOC](#table-of-contents)
* \>
  * Redirect standard output to a given file using `>`. The file will be completely **overwritten**.
    ```s
    command [options and argument] > file_name
    ```
* \>>
  * **Append** the standard output to a given file using `>>`.
    ```s
    command [options and argument] >> file_name
    ```
* 2>
  * Redirect standard error to a given file using `2>`. The file will be completely **overwritten**.
    ```s
    command [options and argument] 2> file_name
    ```
* 2>>
  * **Append** the standard error to a given file using `2>>`
    ```s
    command [options and argument] 2>> file_name
    ```
* <
  * Redirect standard input using `<`.
  * Standard input usually refers to the keyboard. We can use `<` to redirect the standard input from other sources, such as a file.
    ```s
    command [options and argument] < input_file_name // This is different from command [options and argument] input_file_name
    ```
  * I want to use `cat` as an example to further illustrate the differences between `command file_name` and `command < file_name`. 
    * `cat README.md` and `cat < README.md` use different mechanisms although their outputs are identical. 
      * Here is the user manual of `cat` command:
        ```
        NAME
         cat - concatenate files and print on the standard output

        SYNOPSIS
              cat [OPTION]... [FILE]...

        DESCRIPTION
              Concatenate FILE(s) to standard output.

              With no FILE, or when FILE is -, read standard input.
        ...
        ```
      * `cat README.md` use SYNOPSIS format: `cat [OPTION]... [FILE]...`. So README.md is a FILE for cat command.
      * `cat < README.md` means there is no FILE for cat, so "read standard input" instead. "< README.md" is the standard input.
### Piping
[Back to TOC](#table-of-contents)
* |
  * We use the pipe character(`|`) to connect two commands. The output of the first command will be passed to the standard input of the second command.
    ```s
    command_1 | command_2
    ```
  * examples of using piping:
    ```s
    ls /bin -l | less
    ls /bin -l | wc -l
    ncal | tac | rev  // pip three commands
    ```
* tee
  * The tee command reads the standard input and **copies** the standard input **both** to the standard output **AND** to a file. 
  * This allows to capture information part of the way through a pip without interrupting the flow. 
  * Examples:
    ```s
    command_1 | tee output_file | command_2
    cat README.md | tee output.txt | wc -w
    du -ha /usr/bin/ | sort -h | tee sizes.txt | tail -4 | head -3
    ```
    * `cat README.md | tee output.txt | wc -w`: `cat` read the README.md file. Then, `tee` took the standard output from `cat` as its own standard input, wrote this standard input into output.txt, and sent the same information as standard output of `tee`. Then, `wc -w` took the standard output from `tee` as its own standard input and count number of words and sent out the result (word count) as standard output. 
### Finding things
[Back to TOC](#table-of-contents)
* locate
* find
## Useful commands
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
    history // this list the history commands with id
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
    * An executable program which usually stored in /bin, /usr/bin, or /usr/local/bin. These are compiled binary files (hence bin)
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

## Nice to have commands
[Back to TOC](#table-of-contents) 
* date
  * Print out the time of the system
* ncal 
  * Print out a vertical calender of current month
  * Print out the calendar of the entire year: 
    ```s
    ncal 2025
    ```
  * Print out the calendar of a given month in a given year
    ```s
    ncal jan 2022
    ```
## Shortcuts
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
* **Ctrl + d**: kill the character in the current cursor.

## Expansion
[Back to TOC](#table-of-contents)
* Pathname expansion
  * Wildcard characters:
    | character | meaning | example |
    | :-------: | :--------------------------------:| :---------------- |
    | * | Represent **zero or more** characters | `cat *.txt`       |
    | ? | Represent any **single** character | `ls pic?.png`     |
    | [] | Inside of square brackets we can specify **a range of** characters to match  | `ls [A-F]*.txt` | 
    | [^] | Inside of square brackets we can specify **a range of** characters to **NOT** match | `ls [^aApP]*.txt` |
* Tilde expansion
  * `~` expansion refers to the HOME directory of the current user.
    ```s
    ls ~/Documents
    ```
* Brace expansion
  * Brace expression (`{}`) is used to generate arbitrary strings. Basically, it will generate multiple strings for us based on a pattern. We provide a set of strings inside of braces, as well as optional surrounding prefix and suffixes.
  * The specified strings are used to generate all possible combinations with optional prefixes and suffixes. 
  * The command below will create three files: page1.txt, page2.txt, page3.txt
    ```s
    touch page{1,2,3}.txt
    ```
  * The command below will create 5 files based on the range {1..5}: t1.txt, t2.txt, t3.txt, t4.txt, t5.txt
    ```s
    touch t{1..5}.txt
    ```
  * We can also provide an interval like this example below
    ```s
    mkdir t{1..10..4} // {1..10..4} means increasing from 1 to 10 with an interval of 4
    ```
  * {} works for the letters as well
    ```s
    echo {a..m}
    ```
  * We can next {} inside a {}
    ```s
    echo {x,y{1..5},z} // output: x y1 y2 y3 y4 y5 z
    ```
* Arithmetic expansion
  * The shell perform arithmetic via expansion using the `$((arithmetic expression))` syntax.
    ```s
    echo $((2+3))  // output: 5
    echo $((2**5)) // output: 32
    ```
    | operator | meaning |
    | :----: | :------ |
    | + | addition |
    | - | subtraction |
    | * | multiplication |
    | / | division |
    | ** | exponentiation |
    | % | modulo (reminder operator)
  * Arithmetic expression in bash seems to only work with whole number, such as long and integer.
* Quoting expansion
  * Double quotes (`" "`)
    * If we wrap text in double quotes, the shell will respect our spacing and will ignore special characters **except for dollar sign ($), backslash (\\), and back ticks (`)**.
      ```s
      echo "look at   me"     // output: look at   me
      echo "{1..9"}           // output: {1..9}
      echo "path: $PATH"      // output: path: /usr/local/sbin:/usr/local/bin:/usr/sbin
      echo "today is $(date)" // output: today is Tue 04 Jan 2022 07:36:28 AM CST
      ```
    * Pathname expansion, brace expansion, and word splitting will be ignored.
    * However, command substitution and arithmetic expansion are still performed because dollar sign still have meaning inside of double quote
  * Single quotes (`' '`)
    * Single quotes in shell suppress all forms of substitutions.
      ```s
      echo 'path: $PATH'      // output: path: $PATH
      echo 'today is $(date)' // output: today is $(date)
      ```
* Command substitution
  * We can use `$(command_2)` syntax to display output of this command_2.
    ```s
    echo "today is $(date)" // output: today is Tue 04 Jan 2022 07:36:28 AM CST
    ```
  * We can also use `` syntax to display output of command inside of back ticks.
    ```s
    echo "today is `date`" // output: today is Tue 04 Jan 2022 07:36:28 AM CST
    echo today is `date`   // output: today is Tue 04 Jan 2022 07:36:28 AM CST
    `echo node`            // This will open the node console for me 
    ```
  
