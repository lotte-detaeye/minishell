# Minishell Project

## Overview
The **Minishell** project involves building a simple shell in C that emulates some of the core functionalities of Bash. 
This project covers the implementation of built-in commands, input/output redirections, piping between processes, and handling heredoc syntax. 
The goal was to deepen our understanding of process management, file descriptors, and system calls in Unix-like operating systems.

## Features
- **Built-in Commands:**
  - `echo`
  - `cd`
  - `pwd`
  - `export`
  - `unset`
  - `env`
  - `exit`
- **Redirections:**
  - Input redirection (`<`)
  - Output redirection (`>` and `>>`)
- **Pipes:**
  - Chaining commands using the pipe operator (`|`)
- **Heredocs:**
  - Support for `<<` syntax to handle multi-line input until a specified delimiter
- **Signal Handling:**
  - Proper handling of `Ctrl+C`, `Ctrl+D`, and `Ctrl+\` signals to mimic Bash behavior

## Requirements
- The project must be written in **C**
- The shell should work on Unix-like systems
- Proper memory management is mandatory (no memory leaks)

## Compilation
Use the provided **Makefile** to compile the project:
```bash
make
```
This will generate the `minishell` executable.

## Usage
Launch the shell by running:
```bash
./minishell
```
Example commands you can try:
```bash
$ echo Hello, world!
$ ls -l | grep minishell
$ cat << EOF
This is a heredoc example.
EOF
$ export VAR=value
$ echo $VAR
```

## Built-in Commands
| Command   | Description                    |
|-----------|--------------------------------|
| `echo`    | Prints text to the terminal     |
| `cd`      | Changes the current directory   |
| `pwd`     | Prints the current directory    |
| `export`  | Sets environment variables      |
| `unset`   | Unsets environment variables    |
| `env`     | Displays all environment variables |
| `exit`    | Exits the shell                 |

## Signal Handling
| Signal    | Behavior                        |
|-----------|---------------------------------|
| `Ctrl+C`  | Interrupts the current command  |
| `Ctrl+D`  | Exits the shell                |
| `Ctrl+\`  | Quits the current process       |

## Redirections and Pipes
- **Input Redirection (`<`)**: Redirects input from a file
- **Output Redirection (`>`)**: Redirects output to a file, truncating it if it exists
- **Append Redirection (`>>`)**: Redirects output to a file, appending if it exists
- **Pipes (`|`)**: Connects the output of one command to the input of another
- **Heredocs (`<<`)**: Accepts multi-line input until a specified delimiter is reached

## Error Handling
- Proper error messages for invalid commands
- Graceful handling of file descriptor errors
- Handling of invalid syntax for redirections and pipes

## Memory Management
- Ensure all allocated memory is freed
- Handle errors related to `malloc` and `free`

## Future Improvements
- Implement wildcard expansion (`*`)
- Add support for `&&` and `||` operators

## Acknowledgments
Thanks to @n-andr for being an amazing partner who I learned a lot from

