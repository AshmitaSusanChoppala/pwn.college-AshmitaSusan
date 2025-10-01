# Pondering PATH

## Challenge 1: The PATH Variable
This challenge deals with the use of "PATH" variable to make commands unable to find.

### Solve
**Flag:** `pwn.college{47s2gCmnI3dOPFZzTADrbyBeDPz.QX2cDM1wCM4EzNzEzW}`

To get the flag, we need to make it so that the "rm" command is not found. To do that, we can use the PATH variable as so, "PATH="rm"". Then, "/challenge/run" was executed. Since, rm command could not be found, the flag was given as the output. Then the flag was copied and pasted into the flag box.

```bash
PATH="rm"
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: command not found
The flag is still there! I might as well give it to you!
pwn.college{47s2gCmnI3dOPFZzTADrbyBeDPz.QX2cDM1wCM4EzNzEzW}
```

### New Learnings
-> There is a special shell variable, called PATH, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands.

### References 
The module instruction was used.



## Challenge 2: Setting PATH
This challenge deals with launching using bare name

### Solve
**Flag:** `pwn.college{QmhY83FOZ8MeoxLSwjWvsCMaI0I.QX1cjM1wCM4EzNzEzW}`

To launch using bare name, PATH variable is used. It is given that "/challenge/more_commands/" is the directory to access the win command. So, "PATH=/challenge/more_commands/" was given as the input to enter the directory. Then "/challenge/run" was executed, which invoked the "win" command and gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{QmhY83FOZ8MeoxLSwjWvsCMaI0I.QX1cjM1wCM4EzNzEzW}
```

### New Learnings
-> by adding directories to or replacing directories in this list, you can expose these programs to be launched using their bare name

### References 
The module instruction was used.



## Challenge 3: Finding Commands
This challenge deals with finding commands using which command

### Solve
**Flag:** `pwn.college{MgJg8uA3r4vX7CWk39AMhT2Ow1n.01NzEzNxwCM4EzNzEzW}`

The flag is in the same directory as the win command, so, the directory of the win command needs to be found out. For this, the which command can be used as so, "which win". The path was given as "/challenge/paths/23186/win", which means the flag is in "/challenge/paths/23186/" directory. Therefore, the file can be read using cat as so, "cat /challenge/paths/23186/flag", which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
which win
/challenge/paths/23186/win
hacker@path~finding-commands:~$ cat /challenge/paths/23186/flag
pwn.college{MgJg8uA3r4vX7CWk39AMhT2Ow1n.01NzEzNxwCM4EzNzEzW}
```

### New Learnings
->  which looks at each directory in $PATH in order and prints the first file it finds whose name matches the argument you passed.

### References 
The module instruction was used.



## Challenge 4:Adding Commands
This challenge deals with using your own commands

### Solve
**Flag:** `pwn.college{oUxq6TmOTlzswMDSSOZPJEJTG0N.QX2cjM1wCM4EzNzEzW}`

First, a temporary directory was created using mkdir as so, "mkdir /tmp/mycommands". Then, the flag contents were written inside win which is created in the temporary directory. Then, it was given permissions for execution and the path of the directory was given to PATH. "/challenge/run" was executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
mkdir /tmp/mycommands
hacker@path~adding-commands:~$ echo 'read FLAG </flag; echo "$FLAG"' > /tmp/mycommands/win
hacker@path~adding-commands:~$ chmod +x /tmp/mycommands/win
hacker@path~adding-commands:~$ PATH=/tmp/mycommands
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{oUxq6TmOTlzswMDSSOZPJEJTG0N.QX2cjM1wCM4EzNzEzW}
```

### New Learnings
-> adding and creating commands

### References 
The module instruction was used.



## Challenge 5: Hijacking Commands
This challenge deals with adding rm command

### Solve
**Flag:** `pwn.college{ct6IwXv2XWsAErVE0f2AAjPrWb2.QX3cjM1wCM4EzNzEzW}`

Since, we need rm command, we need to create a script for it. First, a temporary directory was created using mkdir as so, "mkdir /tmp/commands". Then, the flag contents were written inside win which is created in the temporary directory. Then, it was given permissions for execution and the path of the directory was given to PATH. "/challenge/run" was executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
mkdir /tmp/commands
hacker@path~hijacking-commands:~$ echo 'read FLAG </flag; echo "$FLAG"' > /tmp/commands/rm
hacker@path~hijacking-commands:~$ chmod +x /tmp/commands/rm
hacker@path~hijacking-commands:~$ PATH=/tmp/commands
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
pwn.college{ct6IwXv2XWsAErVE0f2AAjPrWb2.QX3cjM1wCM4EzNzEzW}
```

### New Learnings
-> adding and creating commands

### References 
The module instruction was used.
