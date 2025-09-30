# Perceiving Permissions

## Challenge 1: Changing File Ownership
This challenge deals with changing the ownership of a file, and using chown command to do it

### Solve
**Flag:** `pwn.college{YtWtxzUIQWacg-i4iPe7k3caTZb.QXxEjN0wCM4EzNzEzW}`

Since, for this challenge, we can use "chown" command from "hacker" user itself (generally, can only be done using root), to change the ownership of the flag file "chown hacker /flag" was given as the input. To read the flag cat command was used, as so "cat /flag", which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{YtWtxzUIQWacg-i4iPe7k3caTZb.QXxEjN0wCM4EzNzEzW}
```

### New Learnings
-> The two most important user accounts are:
 - Your user account! On pwn.college, this is the hacker user, regardless of what your username is.
 - root. This is the administrative account and, in most security situations, the ultimate prize. If you take over the root user, you've almost certainly achieved your hacking objective
-> we can change the ownership of files via the chown (change owner) command

### References 
The module instruction was used.



## Challenge 2: Groups and Files
This challenge deals with changing the group ownership of a file, and using chgrp command to do it

### Solve
**Flag:** `pwn.college{QjYMAxlYOPt5e2GgDiZbUJ9s_-m.QXxcjM1wCM4EzNzEzW}`

Since, for this challenge, we can use "chgrp" command from "hacker" user itself (generally, can be done using root), to change the ownership of the flag file "chgrp hacker /flag" was given as the input. To read the flag cat command was used, as so "cat /flag",, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{QjYMAxlYOPt5e2GgDiZbUJ9s_-m.QXxcjM1wCM4EzNzEzW}
```

### New Learnings
-> Files have both an owning user and group. A group can have multiple users in it, and a user can be a member of multiple groups.
-> You can check what groups you are part of with the id command
-> Group ownership can be changed with the chgrp (change group) command. Unless you have write access to the file and membership in the new group, this typically requires root access

### References 
The module instruction was used.



## Challenge 3: Fun with Groups Names
This challenge deals with situations with different group names

### Solve
**Flag:** `pwn.college{UYkzCNhQpgVZSRZhYMQ0PI9BN7c.QXycjM1wCM4EzNzEzW}`

Since, hacker is not allowed for this challenge, the new group must be found. This can be done using id command. The group came to be "grp6628". Now, we need to change the group ownership of the flag file to "grp2688" using the "chgrp" command as so : "chgrp grp6628 /flag". Then, the file was read using cat, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
id
uid=1000(hacker) gid=1000(grp6628) groups=1000(grp6628)
hacker@permissions~fun-with-groups-names:~$ chgrp grp6628 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{UYkzCNhQpgVZSRZhYMQ0PI9BN7c.QXycjM1wCM4EzNzEzW}
```

### New Learnings
-> There is a convention in Linux that every user has their own group, but this does not have to be the case.

### References 
The module instruction was used.



## Challenge 4: Changing Permissions
This challenge deals with changing file permissions

### Solve
**Flag:** `pwn.college{IndVZeriiXl6HrXGMNlKi7T9xvA.QXzcjM1wCM4EzNzEzW}`

To access the file, we have to change the permissions this can be done by "chmod a+r /flag". Then, the file was read using cat, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
chmod a+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{IndVZeriiXl6HrXGMNlKi7T9xvA.QXzcjM1wCM4EzNzEzW}
```

### New Learnings
-> The first character is the file type. The next nine characters are the actual access permissions of the file or directory, split into 3 characters denoting permissions for the owning user, 3 characters denoting the permissions for the owning group, and 3 characters denoting the permissions that all other access has to the file.
-> Each character of the three represent permission for a different type:
r - user/group/other can read the file (or list the directory)
w - user/group/other can modify the files (or create/delete files in the directory)
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)
- - nothing 
-> Like ownership, file permissions can also be changed. This is done with the chmod (change mode) command. The basic usage for chmod is:
chmod [OPTIONS] MODE FILE
-> chmod allows you to tweak permissions with the mode format of WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute.
-> u+r, as above, adds read access to the user's permissions
g+wx adds write and execute access to the group's permissions
o-w removes write access for other users
a-rwx removes all permissions for the user, group, and world

### References 
The module instruction was used.



## Challenge 5: Executable Files
This challenge deals with executing permissions

### Solve
**Flag:** `pwn.college{gFrS9OHQgWfTKbLe1RiZqq9zNYd.QXyEjN0wCM4EzNzEzW}`

To change the file permissions, "chmod" command has to be used. In "a+x", a provides all permissions with x being used for execution. Combining this, "chmod a+x /challenge/run" was given as the input. Then "/challenge/run" was executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
chmod a+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{gFrS9OHQgWfTKbLe1RiZqq9zNYd.QXyEjN0wCM4EzNzEzW}
```

### New Learnings
-> When you invoke a program, Linux will only actually execute it if you have execute-access to the program file

### References 
The module instruction was used.



## Challenge 6: Permissions Tweaking Practice
chmod practice

### Solve
**Flag:** `pwn.college{o7XoZPNBwTn0EnwAiNV4_VTgU8o.QXwEjN0wCM4EzNzEzW}`

A series of challenges were given where we had to set permissions using chmod using the conditions they specify. At the end, permission were set to the flag file and was read, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
pwn.college{o7XoZPNBwTn0EnwAiNV4_VTgU8o.QXwEjN0wCM4EzNzEzW}
```

### New Learnings
-> chmod practice

### References 
The module instruction was used.



## Challenge 7: Permissions Setting Practice 
Setting permission using chmod and chaining(= and ,)

### Solve
**Flag:** `pwn.college{g1oCD88jYACbdQhjjco3nL2ltfK.QXzETO0wCM4EzNzEzW}`

A series of challenges were given where we had to set permissions using chmod using the conditions they specify but only using chaining. At the end, permission were set to the flag file and was read, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
pwn.college{g1oCD88jYACbdQhjjco3nL2ltfK.QXzETO0wCM4EzNzEzW}
```

### New Learnings
-> chmod can also simply set permissions altogether, overwriting the old ones. This is done by using = instead of - or +. 
-> You can chain multiple modes to chmod with ,

### References 
The module instruction was used.



## Challenge 8: The SUID Bit
The objective of the challenge is to add the SUID bit to spawn the root shell

### Solve
**Flag:** `pwn.college{0NjTnHU3is-Zd2nGwOjj0pmvqGt.QXzEjN0wCM4EzNzEzW}`

To add the SUID bit to the /challenge/getroot program, "chmod u+s /challenge/getroot" was executed. The "/challenge/getroot" program was run and now it is running as root. Then, the file was read using cat, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root! 
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{0NjTnHU3is-Zd2nGwOjj0pmvqGt.QXzEjN0wCM4EzNzEzW}

```

### New Learnings
-> The system admin can't be there to give them the password every time a user wanted to do a task that only root/sudoers can do. Instead, the "Set User ID" (SUID) permissions bit allows the user to run a program as the owner of that program's file.
-> The s part in place of the executable bit means that the program is executable with SUID. It means that, regardless of what user runs the program (as long as they have executable permissions), the program will execute as the owner user (in this case, the root user).
-> As the owner of a file, you can set a file's SUID bit by using chmod:
chmod u+s [program]

### References 
The module instruction was used.