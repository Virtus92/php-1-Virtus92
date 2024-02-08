# Absolute vs. relative paths
Absolute and relative paths describe the location of a file or directory within a file system. An absolute path describes the exact location of a file on a computer. A relative path describes the location of one file in relation to the current working directory.

## What is an absolute path?
Depending on the OS (Operating System) type, an absolute path is presented differently. The start of the absolute path is the root directory. It is represented as a forward slash (/) in Unix-like operating systems or as a drive letter and backslash in Windows.

An example of an absolute path in Linux:
```
/home/user/documents/file.txt
```
In Windows:
```
C:\Users\User\Documents\file.txt
```
Both paths start from the beginning of the drive or root directory and lead up to the file.txt file.

## What is a relative path?
A relative path is the location of a file or directory relative to your current working directory. Unlike an absolute path, the relative path doesn't start with a slash or drive letter since it doesn't start from the root directory.

Relative paths simplify working with files by minimizing the typing needed to specify the file or directory path. A relative path is used whenever you refer to a file or directory only by its name. That is the simplest form of a relative path, and the shell looks for the specified file name within the current directory.

Relative paths adapt to changes in the current working directory, making them convenient for scripting, development, and file management within a localized context.

**In Linux:**
```
file.txt
```
The system looks for the specified file in the current working directory.
```
./reports/report.txt
```

**In Windows:**

When you are currently located in the directory C:\Users\John\Documents, and you want to reference a file named document.txt in the current directory, use the following relative path:
```
.\document.txt
```
If you want to specify a file named invoice.pdf in a subdirectory called invoices within the current directory, use the following relative path:
```
.\invoices\invoice.pdf
```

When a php file includes another file, it is good practice to use absolute paths. 