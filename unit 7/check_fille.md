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

## the line by line explation of the code is :-
```
#!/bin/bash
→ Shebang line, tells the system to use bash to run this script.

2–3. Comments explaining the script name and usage.

4–7.

if [ $# -ne 1 ]; then
  echo "Usage: $0 <filename>"
  exit 1
fi


$# = number of command-line arguments.

If not equal to 1, print usage and exit.

$0 is the script name itself.

👉 Ensures the user must provide one filename.

file="$1"

$1 is the first argument passed (the filename).

Stores it in variable file.

10–14.

if [ -e "$file" ]; then
  echo "File exists: $file"
  echo "------ contents ------"
  cat -- "$file"


-e "$file" checks if the file exists.

If yes → print confirmation and display its contents using cat.

15–21 (else part):
If the file does not exist:

Inform the user: "File '$file' does not exist."

Ask: "Create it now? (y/N): "

Use a case statement:

If answer starts with y or Y → touch creates an empty file, then prints confirmation.

Otherwise → "Not creating file."

✅ What this script does

Takes a filename as input.

If file exists → shows its contents.

If file does not exist → asks user whether to create it.

👉 Example run:

$ ./check_file.sh notes.txt
File 'notes.txt' does not exist.
Create it now? (y/N): y
Created notes.txt
You can edit it using nano/vi/etc. 

```
