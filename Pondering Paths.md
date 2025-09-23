# Pondering Paths

## Challenge 1: The root
Invoking the program using the root directory

### Solve
**Flag:** `pwn.college{odbDvZyXTb8QvD2WoZlYGTOGz1u.QX4cTO0wCM4EzNzEzW}`

The challenge is to invoke a program by provinding its path on the command line. In this challenge, we need to access the program pwn. Since, it is an absolute path (as the program is added in /), we can access it by using "/pwn" in the terminal. The output is the flag. Then the flag was copied and pasted into the flag box.

```bash
/pwn
Here is your flag:
pwn.college{odbDvZyXTb8QvD2WoZlYGTOGz1u.QX4cTO0wCM4EzNzEzW}
```

### New Learnings
-> The filesystem starts at /(Root directory).
-> Directories contain files and other directories, root directory is like the main directory/"outerbox" which contains all the directories.
-> File can be accessed by specifying its path.
-> The style of path that starts with the root directory is referred to as an absolute path.

### References 
The module instruction was used.



## Challenge 2: Program and absolute paths
This challenge focuses on accessing program with a bit more complicated path

### Solve
**Flag:** `pwn.college{knj_s5j21oPJ0HDyY2sqMZl4DU7.QX1QTN0wCM4EzNzEzW}`

The challenge is to access the run program which is not directly in the root directory. The run program is in the challenge directory which is in the root directory. Therefore the run program can be accessed by using the path "/challenge/run" in the terminal. The output is the flag. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{knj_s5j21oPJ0HDyY2sqMZl4DU7.QX1QTN0wCM4EzNzEzW}
```

### New Learnings
-> Programs not in the root directory directly can be accessed by "/directory1/directory2/.../program name", where directory 2 is in directory 1 and so on and each directory/program are seperated by a forward slash "/".

### References 
The module instruction was used.



## Challenge 3: Position thy self
This challenge helps us understand the cd command and how it is executed, also tells us about the etc directory.

### Solve
**Flag:** `pwn.college{helloworld}`

The challenge is to access the run program which is in challenge directory which is in another directory. First, we used the "/challenge/run" to know the common directory, which was given in the output. The common directory was given as /etc. Therefore, the command "cd /etc" was used to enter/ access the common directory. When it entered in the common directory which is shown as "/etc$", "/challenge/run" was executed in the terminal which gave the output as the flag. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run
Incorrect...
You are not currently in the /etc directory.
Please use the `cd` utility to change directory appropriately.
cd /etc
hacker@paths~position-thy-self:/etc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{oilSjnDCU_uMrxjvXI4EpPWONtc.QX2QTN0wCM4EzNzEzW}
```

### New Learnings
-> cd(change directory) command can be used to naviagate around directories, with path as the argument.
-> cd command also affects the current working directory.
-> ~ shows the current path that your shell is located at.
-> /etc - system configuration - stores system wide configuration files and directories


### References 
The module instruction and the ppt at the beginning of the module was used.



## Challenge 4: Position Elsewhere
This challenge helps us understand the cd command and how it is executed and how it can be used when more than one directory is there and, also tells us about the sys directory.

### Solve
**Flag:** `pwn.college{81ql2kcCXcfNld8t39rHLRC1k26.QX3QTN0wCM4EzNzEzW}`

The challenge is to access the run program which is in challenge directory which is in another directory. First, we used the "/challenge/run" to know the common directory, which was given in the output. The common directory was given as /sys/kernel. Therefore, the command "cd /sys/kernel" was used to enter/ access the common directory. When it entered in the common directory which is shown as "/sys/kernel$", "/challenge/run" was executed in the terminal which gave the output as the flag. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run
Incorrect...
You are not currently in the /sys/kernel directory.
Please use the `cd` utility to change directory appropriately.
cd /sys/kernel
hacker@paths~position-elsewhere:/sys/kernel$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{81ql2kcCXcfNld8t39rHLRC1k26.QX3QTN0wCM4EzNzEzW}
```

### New Learnings
-> cd(change directory) command can be used to naviagate around directories, with path as the argument, multiple directories can also be referenced using the cd command.
-> cd command also affects the current working directory.
-> ~ shows the current path that your shell is located at.
-> /sys is a virtual file system that can be accessed to set or obtain information about the kernel's view of the system.

### References 
the module instruction was used.
https://askubuntu.com/questions/720471/whats-the-sys-directory-for



## Challenge 5: Position yet Elsewhere
This challenge helps us understand the cd command and how it is executed and also tells us about the home directory.

### Solve
**Flag:** `pwn.college{helloworld}`

The challenge is to access the run program which is in challenge directory which is in another directory. First, we used the "/challenge/run" to know the common directory, which was given in the output. The common directory was given as /home. Therefore, the command "cd /home" was used to enter/access the common directory. When it entered in the common directory which is shown as "/sys/kernelhome$", "/challenge/run" was executed in the terminal which gave the output as the flag. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run
Incorrect...
You are not currently in the /home directory.
Please use the `cd` utility to change directory appropriately.
cd /home
hacker@paths~position-yet-elsewhere:/home$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{0ah9_QSDxOrJqfFBMpO0z4yAn6s.QX4QTN0wCM4EzNzEzW}
```

### New Learnings
-> cd(change directory) command can be used to naviagate around directories, with path as the argument, multiple directories can also be referenced using the cd command.
-> cd command also affects the current working directory.
-> ~ shows the current path that your shell is located at.
-> /home - user-owned data - serves as a personal directory where user can store personal files, documents etc.

### References 
The module instruction and the ppt at the beginning of the module was used.



## Challenge 6: implicit relative paths, from /
This challenge emphasises on the concept of relative paths and how current working directory is important to it.

### Solve
**Flag:** `pwn.college{0bRdOHJoGXJDTgoobyLVteRuD5J.QX5QTN0wCM4EzNzEzW}`

The challenge is to access the run program which is in the challenge directory and to access this directory. It was given that the common working directory should be "/". "cd /" command was executed to enter the common working directory. The relative path is "challenge/run" which was executed in the terminal which in turn gave flag as the output. Then the flag was copied and pasted into the flag box.

```bash
cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{0bRdOHJoGXJDTgoobyLVteRuD5J.QX5QTN0wCM4EzNzEzW}
```

### New Learnings
-> The current working directory(cwd) does matter for relative paths.
-> A relative path is any path that does not start at root.
-> A relative path is interpreted relative to your current working directory (cwd).
-> Your cwd is the directory that your prompt is currently located at.
-> implicit paths - it directly specifies the directory to descend into from the current directory.

### References 
The module instruction was used.



## Challenge 7: explicit relative paths, from /
The challenge specifies the difference between explicit and implicit relative paths and how explicit relative paths are used.

### Solve
**Flag:** `pwn.college{Ar0NEXfYqXDCWKrRitBpYmOE5r3.QXwUTN0wCM4EzNzEzW}`

The challenge is to access the run program which is in the challenge directory and to access this directory. It was given that the common working directory should be "/". "cd /" command was executed to enter the common working directory. The relative path should be explicit, making the command as "./challenge/run" which was executed in the terminal which in turn gave flag as the output. Then the flag was copied and pasted into the flag box.

```bash
cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Ar0NEXfYqXDCWKrRitBpYmOE5r3.QXwUTN0wCM4EzNzEzW}
```

### New Learnings
-> explicit paths - use "./" notation to access files while implicit paths use only "/" notation.
-> "." refers right to the same directory.

### References 
The module instruction was used.



## Challenge 8: implicit relative path
Add challenge description here

### Solve
**Flag:** `pwn.college{AJphWZsaU_VSo7TAfpwiymG2tP0.QXxUTN0wCM4EzNzEzW}`

The challenge is to access the run program which is in the challenge directory and to access this directory. It was given that the common working directory should be "/challenge". "cd /challenge" command was executed to enter the common working directory. It was give that the relative path should be executed explicitly. Therefore, "./run" was executed which gave the output as the flag. Then the flag was copied and pasted into the flag box. 

```bash
cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{AJphWZsaU_VSo7TAfpwiymG2tP0.QXxUTN0wCM4EzNzEzW}
```

### New Learnings
-> Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path.
-> if Linux searched the current directory for programs every time you entered a naked path, you could accidentally execute programs in your current directory that happened to have the same names as core system utilities

### References 
The module instruction was used.



## Challenge 9: home sweet home
This challenge tells about the home directory and it's expansion and how to refer to it.

### Solve
**Flag:** `pwn.college{QQ9TqDP8JKMcqIclpo1E6E_WMSN.QXzMDO0wCM4EzNzEzW}`

The challenge is to use the properties of the home command. It was given that "/challenge/run" is the command and it has an argument which is an absolute path with <=3 characters. The path must be in the home directory. "~" character was used to refer to the home directory which expands to "/home/hacker" and then "/a" (absolute path) was used. The entire absolute path which is the argument is "~/a". The command and argument were executed which gave the output as the flag. Then the flag was copied and pasted into the flag box.

```bash
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{QQ9TqDP8JKMcqIclpo1E6E_WMSN.QXzMDO0wCM4EzNzEzW}
```

### New Learnings
-> Every user has a home directory, typically under /home in the filesystem.
-> The home directory is typically where users store most of their personal files.
-> The expansion of ~ is an absolute path, and only the leading ~ is expanded. 

### References 
The module instruction was used.