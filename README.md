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
* man
  * read the manual page of a command
    ```s
    man ncal
    ```
  * search a command
    ```s
    man -k command_name
    man -k passwd
    ```
  * read the mannual page of a command in a specific session
    ```s
    man 1 passwd
    ```

### Useful commands
* clear
  * clear the terminal
* sort
  * sort each lines in a give file
    ```s
    sort file_name
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
