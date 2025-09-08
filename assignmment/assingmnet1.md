# Assignment 1 – Unit-1: Linux Basics
## Objective: Practice essential Linux commands.
Here's a detailed tutorial on basic terminal commands that work on Linux, macOS, and Git Bash (Windows). These commands are essential for navigating and managing files from the terminal, especially for coding and version control (e.g., Git, VS Code, etc.).

# 1. navigation commands

## pwd - Print Working Directory
shows the current location  in the file system .

``` bash
pwd
```

 output example

``` bash
/home/akshat-mishra/Documents/GitHub/linux-lab
```
![images](./images/ls.png)

## ls - List Directory Contents
lists files and folder in the current directory .
``` bash
ls
```
 ls -l 
     [detailed list( permissions, size, date)]

![images](./images/pn.png)

 ls-a 
  [ shows hidden files(those starting with .)]

![images](./images/pn2.png)

 ls -la
 combined

![images](./images/pn3.png)


## cd - Change Directory
move into  a directory

``` bash
cd folder_name 
```
exmaples


``` bash
cd document          # go to Documents
cd ..                # go up one level    
cd /                 # go to roots 
cd ~                 # go to home directory
```
![images](./images/pn4.png)

# 2. File and Directory Management

##  mkdir - make directory 

create a new folder.

``` bash
mkdir hello_folder
```

![images](./images/pn5.png)

## touch - Create File

create an empty file.

``` bash
touch file.txt
```
![images](./images/pn6.png)

## cp - Copy Files or Directories
``` bash
 cp file.txt file2.txt
 ```

 cp folder:
 ``` bash
 cp -r hello_folder bye_folder
 ```
 ![images](./images/pn7.png)

 ## mv - Move or rename Files

 ```bash
mv oldname.txt newname.txt
 ```

  ```bash
 mv file.txt ~/documents/   # Move file
 ```
![images](./images/pn8.png)

## rm - remove files

 ```bash
 rm file.txt          #delete file
 rm -r folder_name    #delte folder ( recursively)
 ```
 ![images](./images/pn9.png)

##  be careful!
there is no undo

# 3. File Viewing & Editing

## cat - view file contents
Displays content in terminal.
 ```bash
 cat file.txt
 ```
 ![images](./images/pn10.png)

 ## nano -edit file in terminal 
 A basic terminal- based text editor.
  ```bash
  nano file.txt
 ```
 1. use aroow to move
 2. ctrl +o to save
 3. ctrl +x to exit

![images](./images/pn11.png)

## clear - clear the terminal
 ```bash
 clear
 ```
 shortcut : CTRL + L

 ![images](./images/pn12.png)

 # 4 . System Commands

   ## echo - print text

  useful for debugging or scripting.

   ```bash
   echo "hellow world"
 ```
 ![images](./images/pn13.png)
 
  ## whoami - show current user

  ```bash
  whoami
  ```
  ![images](./images/pn14.png)

  ## man- Manual for Any Command

  ```bash
  man ls
  ```
  use q to quit the manual.
  ![images](./images/pn15.png)

  # 5. searching and finding
  
  ## find - locate files

  ``` bash
  find . -name ".txt"
  ```
  find all .txt files in the current folder and subfolders.

  ![images](./images/pn16.png)

  ## grep - Search Inside Files
  ``` bash
  grep"hello" file.txt
  ```
 ![images](./images/pn17.png)

 # 6. helpful shortcut
 
  ![images](./images/pn18.png)

 # 7. Bonus : Chaining Commands
  
   ## run multiple commanands:
   ``` bash
   mkdir test && cd test && touch hello.txt
   ```
   ![images](./images/pn19.png)

   ## run only if previous commnad succeeds:
   ``` bash
   &&
   ```
   ## run regards of sucess
   ``` bash
   ;
   ```