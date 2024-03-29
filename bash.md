# Bash

```bash
#!/bin/bash

echo "Hello, World!"
```

## sudo

repeat last command with sudo

```bash
sudo !!
```

## file system

### change directory

```bash
cd /path/to/directory
```

go to home directory

```bash
cd
```

go back one directory

```bash
cd ../
```

### list files

```bash
ls
```

list all files, including hidden files

```bash
ls -a
```

list files in different directories

```bash
ls /path/to/directory
```

### create files and directories

create a file

```bash
touch file.txt
```

create a directory/folder

```bash
mkdir folder
```

#### write to a file

add Hello, World! in a new line to file.txt

```bash
echo "Hello, World!" > file.txt
```

## Variables

```bash
name="Saracen" #string
age=20 #int
older18=true #bool
averageGrade=4.0 #float
balance=3535664675.757 #double
arrname=(0 1 2 3 4 5 6 7 8 9) #array
```

print variable

```bash
echo $name
```

### system variables

```bash
$USER #returns current username
$BASH #returns bash directory
$BASH_VERSION #returns bash version
$HOME #returns home directory
$PWD #returns current directory
```

## in and output

```bash
echo "enter your name"
read name
echo "Hello, $name"
```

## flow control

### if statement

```bash
if [ condition ]
then
    #statements

elif [ condition ]
then
    #statements
else
    #statements
fi
```

## functions

```bash
function_name() {
    #statements
}
```

call function

```bash
function_name
```
