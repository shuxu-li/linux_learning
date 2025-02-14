# Basic Command Line Usage

In this article, we will go over some fundamental command-line (cmd) commands that are essential for navigating and managing files in a Unix-like system.

## 1. Navigating the File System

- `pwd` (Present Working Directory): Displays the current directory path.
- `~` (Home Directory): Represents the home directory.
- `date`: Prints the current date and time.
- `cat` (Concatenate): Reads the contents of a file and prints them to the terminal or redirects them elsewhere.
- `cd` (Change Directory): Used to navigate between directories.

  ```bash
  cd ..   # Move to the parent directory
  cd .    # Stay in the current directory
  ```

## 2. Listing Files and Directories

The `ls` command lists the files and directories in the current location:

```bash
$ ls
CV-john.pdf  Calendrier.docx  Calendrier.pdf  Lettre.pdf  ebook  mapped_lfs.json  py-perfectionner  shell
```

To list files in a specific directory:

```bash
$ ls documents/shell   
explore    hello.txt  hello2.txt  missing
```

For detailed information about the `ls` command, use:

```bash
man ls  # Opens the manual for the ls command
```

To display detailed file information:

```bash
$ ls -l

total 16
drwxr-xr-x  5 user  staff  160 Jan 23 17:55 explore
-rw-r--r--  1 user  staff    6 Jan  2 01:08 hello.txt
-rw-r--r--  1 user  staff    6 Jan  2 01:12 hello2.txt
```

## 3. Understanding File Permissions

In the `ls -l` output:
- `d` at the beginning indicates a directory.
- `r` (read), `w` (write), and `x` (execute) specify permissions.
- For a file:
  - Read (`r`): Allows reading the content.
  - Write (`w`): Allows modifying the file.
  - Execute (`x`): Allows running the file as a program.
- For a directory:
  - Read (`r`): Allows listing its contents.
  - Write (`w`): Allows creating, renaming, or deleting files inside.
  - Execute (`x`): Allows accessing the directory.

> **Tip:** If you have write permission on a file but not on its directory, you can modify its content but cannot delete it.

## 4. Managing Files and Directories

- `mv <old_path> <new_path>`: Moves or renames a file.
- `cp <source> <destination>`: Copies a file to another location.
- `rm <file>`: Deletes a file.
- `rmdir <directory>`: Deletes an empty directory.
- `mkdir <directory>`: Creates a new directory.

## 5. Working with Streams

By default, Unix systems have two standard streams:
- **Input stream**: Accepts input from the keyboard.
- **Output stream**: Prints results to the terminal.

Shell allows redirection of these streams using:
- `< file`: Redirects input from a file.
- `> file`: Redirects output to a file (overwrites existing content).
- `>> file`: Appends output to a file without overwriting.

Example:

```bash
$ echo "hello world" > hello.txt  # Writes "hello world" into hello.txt
$ cat hello.txt >> hello2.txt     # Appends hello.txt content to hello2.txt
```

## 6. Using Pipes for Data Processing

The pipe (`|`) operator allows chaining commands by using the output of one command as input for another.

Example:

```bash
$ ls -l | tail -n1   # Displays only the last line of the ls output
```

This technique is widely used for data processing and text manipulation.

## 7. Working as a Superuser (Root)

The root user has unrestricted access to the system, even to files that are unreadable or unwritable by others. To execute commands with superuser privileges, use:

```bash
sudo <command>
```

For example:

```bash
sudo rm protected-file.txt
```

> **Warning:** Use `sudo` with caution, as it can modify critical system files.

## Conclusion

Understanding these basic commands will significantly improve your efficiency when working with the command line. Mastering navigation, file manipulation, and stream redirection will help you work more effectively in a Unix-based environment.
