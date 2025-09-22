# Hello Hackers

## Challenge 1: Intro to Commands
This challenge is helpful to invoke commands such as whoami and hello

### Solve
**Flag:** `pwn.college{IQVXlxyHPC7v7EI3bwOc4wtTZlf.QX3YjM1wCM4EzNzEzW}`

I have executed the commands given by the module to capture the flag. First, I executed the whoami command which gave me the username which is "hacker". Then, I executed the hello command which gave the flag as the output. I copied the flag(By right click then copy) into the clipboard of the desktop and then copied the flag from this clipboard to the clipboard of my laptop and pasted it in the flag box. 

```bash
whoami
hacker
hello
pwn.college{IQVXlxyHPC7v7EI3bwOc4wtTZlf.QX3YjM1wCM4EzNzEzW}
```

### New Learnings
I have learnt that:
-> The whoami command prints the username to the terminal. 
-> Linux commands are case sensitive

### References 
None (only the module instruction was used)



## Challenge 2: Intro to Arguments
This challenge introduces us to command with arguments ,how to execute them and their outputs.

### Solve
**Flag:** `pwn.college{E_-Qm9duDCoTfEQUddl_kqbjoeB.QX4YjM1wCM4EzNzEzW}`

I have executed the commands given by the module to capture the flag. I executed the hello command with the argument hackers which gave the flag as the output.I copied the flag(By right click then copy) into the clipboard of the desktop and then copied the flag from this clipboard to the clipboard of my laptop and pasted it in the flag box.

```bash
hello hackers
pwn.college{E_-Qm9duDCoTfEQUddl_kqbjoeB.QX4YjM1wCM4EzNzEzW}
```

### New Learnings
-> executed commands with arguments (additional data passed to the command)
-> echo command - prints the arguments back to the terminal

### References 
None (only the module instruction was used)



## Challenge 3: Command History
Accessing the history of the shell.

### Solve
**Flag:** `pwn.college{kxJ6OxGpLmSWXKS7ukGTg8hDilh.0lNzEzNxwCM4EzNzEzW}`

I have executed the commands given by the module to capture the flag. I used the up/down arrow to scroll through the history of the shell which gave me the flag as the output.I copied the flag(By right click then copy) into the clipboard of the desktop and then copied the flag from this clipboard to the clipboard of my laptop and pasted it in the flag box.

```bash
hello hackers
-bash: hello: command not found
the flag is pwn.college{kxJ6OxGpLmSWXKS7ukGTg8hDilh.0lNzEzNxwCM4EzNzEzW}
-bash: the: command not found
```

### New Learnings
-> shell saves a history of every command you invoke.
-> commands can be accessed using up/dpwn arrow key.

### References 
None (only the module instruction was used)