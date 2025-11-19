# shell Tutorial - File Permissions with ``` bash chmod``` and ``` chown ```

🔹 1. Understanding File Permissions in Linux

Each file/directory in Linux has:

    Owner → The user who created the file.
    Group → A group of users who may share access.
    Others → Everyone else.

Permission Types

    r → Read (4 in numeric)
    w → Write (2 in numeric)
    x → Execute (1 in numeric)

Permission 

exmaple from  ``` bash ls -l```

![images](./image%20for%20experiment%205/f1.png)

## 🔹 2. chmod – Change File Permissions
Syntax

``` bash

chmod [options] mode filename

```

 ![images](./image%20for%20experiment%205/f2.png)

   Modes can be set in numeric (octal) or symbolic form.

(A) Numeric (Octal) Method

Each permission is represented as a number:

    Read = 4
    Write = 2
    Execute = 1

Add them up:

    7 = rwx
    6 = rw-
    5 = r-x
    4 = r--
    0 = ---

Example:

chmod 755 script.sh

Meaning:

    Owner: 7 → rwx
    Group: 5 → r-x
    Others: 5 → r-x


 ![images](./image%20for%20experiment%205/f3.png)

(B) Symbolic Method

Use u (user/owner), g (group), o (others), a (all). Operators:

    + → Add permission
    - → Remove permission
    = → Assign exact permission

Examples:

chmod u+x script.sh     # Add execute for owner
chmod g-w notes.txt     # Remove write from group
chmod o=r file.txt      # Set others to read only
chmod a+r report.txt    # Everyone gets read access

(C) Recursive Changes

chmod -R 755 /mydir

    ``` bash -R → applies changes recursively to all files/subdirectories.

 ![images](./image%20for%20experiment%205/r%20dis.png)

 after use of recrsive changes   


 ![images](./image%20for%20experiment%205/photo%20gnu.png)

  3. chown – Change File Ownership
Syntax

``` bash
chown [options] new_owner:new_group filename
```
Examples:

``` bash
chown vibhu file.txt           # Change owner to user 'vibhu'
chown vibhu:dev file.txt       # Change owner to 'vibhu' and group to 'dev'
chown :dev file.txt            # Change only group to 'dev'
chown -R vibhu:dev /project    # Recursive ownership change
```

![images](./image%20for%20experiment%205/chown%20owner%20ak.png)

## 🔹 4. Putting It All Together
Example Scenario
``` bash
touch project.sh
ls -l project.sh
```

![images](./image%20for%20experiment%205/puting%20it%20all%20togeather.png)

`
Output:
``` bash
-rw-r--r-- 1 vibhu dev 0 Aug 19 12:00 project.sh
```
Now:
``` bash
chmod 700 project.sh       # Only owner has rwx
chmod u+x,g-w project.sh   # Add execute for user, remove write for group
chown root:admin project.sh # Change owner to root and group to admin
```

1.

![images](./image%20for%20experiment%205/put%20in%20all%20%202nd.png)

2.
![images](./image%20for%20experiment%205/put%20in%20all%203.png)

3.
![images](./image%20for%20experiment%205/all%20togeater%204.png)


## 5. quick refrence table 

![images](./image%20for%20experiment%205/5.png)

key tip: use numberic for quick setting (e.g. , 755,644) and symbolic for fine adjustments( u+x, g-w)