# experiment 1 : check_file.sh

## in the code mentioned belkow we have used a shell scripting to check wheter a file exist or not 
```
# !/bin/bash
# check_file.sh
# Usage: ./check_file.sh filename.txt

if [ $# -ne 1 ]; then
  echo "Usage: $0 <filename>"
  exit 1
fi

file="$1"
if [ -e "$file" ]; then
  echo "File exists: $file"
  echo "------ contents ------"
  cat -- "$file"
else
  echo "File '$file' does not exist."
  read -p "Create it now? (y/N): " ans
  case "$ans" in
    [Yy]*) touch "$file"; echo "Created $file"; echo "You can edit it using your favorite editor." ;;
    *) echo "Not creating file." ;;
  esac
fi
```
## the script can be divide into further various section:-
### 1. shebang


![images](./photos%20of%20%20exp%201/1.png)
```
The bash script check_file.sh is a script that checks if a file exists and if it is a regular file. It takes a filename as a command-line argument and prints a message indicating whether the file meets these conditions.
```

 ### 2. To check the file 

![images](./photos%20of%20%20exp%201/2.png)
```
The code checks  if the number of command- line  arguments passed to the scripot is not equal to one . if the conditon is true , the script  prinmta " usage message and exits the with an error code. 
```
### 3.  to display thwe content of file else ask user ton usaer to craete new file

![images](./photos%20of%20%20exp%201/k.png)

```
The provided script checks for the existence of a file given as a command-line argument. If the file exists, it displays its contents. If the file does not exist, it prompts the user to create it, and if the user confirms, it creates an empty file.
```

## in the code we use command as 

### echo: Displays a line of text to standard output.

### cat: Prints the contents of a file to standard output. When used with the -- option, it prevents cat from interpreting any following arguments starting with a hyphen (-) as command-line options.

### read: Reads a line of text from standard input and stores it in a variable. The -p option allows a prompt to be displayed to the user.

### touch: Creates an empty file if it does not exist. If the file already exists, it updates the file's access and modification timestamps.  