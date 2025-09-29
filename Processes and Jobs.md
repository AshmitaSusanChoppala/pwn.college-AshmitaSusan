# Processes and Jobs

## Challenge 1: Listing Processes
This challenge deals with the use and implementation of ps command

### Solve
**Flag:** `pwn.college{YTzMIqJyjyurGzdCkHk52JQi-xL.QX4MDO0wCM4EzNzEzW}`

First, "ps -ef" was given as the input to list the running process which gave the file name to get the flag. Then the filename "/challenge/8107-run-5741" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
ps -ef
/challenge/8107-run-5741
Yahaha, you found me! Here is your flag:
pwn.college{YTzMIqJyjyurGzdCkHk52JQi-xL.QX4MDO0wCM4EzNzEzW}
```

### New Learnings
-> ps command can be used to list running processes.
-> ps either stands for "process snapshot" or "process status"
-> each process has a numerical identifier (the Process ID, or PID), which is a number that uniquely identifies every running process in a Linux environment.
-> We also see the terminal on which the commands are running and the total amount of cpu time that the process has eaten up so far
-> "Standard" Syntax: in this syntax, you can use -e to list "every" process and -f for a "full format" output, including arguments. These can be combined into a single argument -ef.
"BSD" Syntax: in this syntax, you can use a to list processes for all users, x to list processes that aren't running in a terminal, and u for a "user-readable" output. These can be combined into a single argument aux.

### References 
The module instruction was used.



## Challenge 2: Killing Processes
This challenge deals with the use and implementation of kill command

### Solve
**Flag:** `pwn.college{gSOv6EZQEjjul-LydSLIaqB04iE.QXyQDO0wCM4EzNzEzW}`

First, to get the PID of the "/challenge/dont_run" it was executed in another terminal. Then, in the main terminal, "ps -e | grep dont_run" was run to get the PID and terminated using "kill 355". But, this gave the PID of the grep process and this might be running under another name. Therefore, the main bash itself was found using "ps -e | grep bash" terminated using "kill 136". Then, "/challenge/run" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
ps -e | grep dont_run
    355 pts/0    00:00:00 dont_run
hacker@processes~killing-processes:~$ kill 355
hacker@processes~killing-processes:~$ ps -e | grep bash
    136 ?        00:00:00 bash
    346 pts/0    00:00:00 bash
    361 pts/1    00:00:00 bash
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{gSOv6EZQEjjul-LydSLIaqB04iE.QXyQDO0wCM4EzNzEzW}
```

### New Learnings
-> In Linux, terminating processes is done using the kill command. 
-> Sleep is a program that simply hangs out for the number of seconds specified on the commandline, in this case, 1337 seconds

### References 
The module instruction was used.



## Challenge 3: Interrupting Processes
This challenge deals with the use and implementation of ctrl-c command

### Solve
**Flag:** `pwn.college{waLMSWvM0C0ype_bDmBD7UWLVQI.QXzQDO0wCM4EzNzEzW}`

First, "/challenge/run" was executed and then interrupted (force exit) by ctrl-c "^C" which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{waLMSWvM0C0ype_bDmBD7UWLVQI.QXzQDO0wCM4EzNzEzW}
```

### New Learnings
->  Ctrl-C sends an "interrupt" to whatever application is waiting on input from the terminal and causes the application to cleanly exit.

### References 
The module instruction was used.



## Challenge 4: Killing Msbehaving Processes
This challenge deals with the killing of misbehaving processes

### Solve
**Flag:** `pwn.college{k9fStUL-5YX48_wj5pK3C0mDFW4.0FNzMDOxwCM4EzNzEzW}`

First, "/tmp/flag_fifo" was run in another terminal. Then, in the main terminal, decoy was searched in all the running processes using "ps -e | grep decoy" and then killed using the "kill" command. "/challenge/run" was executed and the new flag entered in the other terminal is the flag required. Then the flag was copied and pasted into the flag box.

```bash
ps -e | grep decoy
    142 ?        00:00:00 decoy
hacker@processes~killing-misbehaving-processes:~$ kill 142
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
```

### New Learnings
-> Applying what was previously learnt

### References 
The module instruction was used.



## Challenge 5: Suspending Processes
The challenge deals with suspending processes using "ctrl-z"

### Solve
**Flag:** `pwn.college{MUDCo0ci2t7YOfSpvUtPIKcuyYC.QX1QDO0wCM4EzNzEzW}`

First, "/challenge/run" was executed and then suspended using "ctrl-z". Then, "/challenge/run" was executed again, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!
UID          PID    PPID  C STIME TTY          TIME CMD
root         340     331  0 04:40 pts/0    00:00:00 bash /challenge/run
root         342     340  0 04:40 pts/0    00:00:00 ps -f
I don't see a second me!
To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!
UID          PID    PPID  C STIME TTY          TIME CMD
root         340     331  0 04:40 pts/0    00:00:00 bash /challenge/run
root         347     331  0 04:40 pts/0    00:00:00 bash /challenge/run
root         349     347  0 04:40 pts/0    00:00:00 ps -f
Yay, I found another version of me! Here is the flag:
pwn.college{MUDCo0ci2t7YOfSpvUtPIKcuyYC.QX1QDO0wCM4EzNzEzW}
```

### New Learnings
-> Ctrl-Z can be used to suspend processes to the background 

### References 
The module instruction was used.



## Challenge 6: Resuming Processes
Resuming processes using fg command

### Solve
**Flag:** `pwn.college{M95QBgKQ9WO_-saaZ2ZPbkjo-Uj.QX2QDO0wCM4EzNzEzW}`

First, "/challenge/run" was executed and then suspended using "ctrl-z" and then resumed again using "fg /challenge/run" as the input, which gave the flag as the output. Enter had to pressed to quit the process. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg /challenge/run
/challenge/run
I'm back! Here's your flag:
pwn.college{M95QBgKQ9WO_-saaZ2ZPbkjo-Uj.QX2QDO0wCM4EzNzEzW}
Don't forget to press Enter to quit me!

Goodbye!
```

### New Learnings
-> To resume processes, your shell provides the fg command, a builtin that takes the suspended process, resumes it, and puts it back in the foreground of your terminal

### References 
The module instruction was used.



## Challenge 7: Backgrounding Processes
Resuming processes in the background using bg command

### Solve
**Flag:** `pwn.college{gKJYnerSA6xq9k4ItpqSLa-W756.QX3QDO0wCM4EzNzEzW}`

First, "/challenge/run" was executed and then suspended using "ctrl-z" and then resumed again using "bg /challenge/run" which got executed in the background, enter was pressed to quit it and "/challenge/run" was given as the input, which gave the flag as the output as two instances of "/challenge/run" was found running. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!
UID          PID STAT CMD
root         339 S+   bash /challenge/run
root         341 R+   ps -o user=UID,pid,stat,cmd
I don't see a second me!
To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         339 S    bash /challenge/run
root         349 S    sleep 6h
root         350 S+   bash /challenge/run
root         352 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{gKJYnerSA6xq9k4ItpqSLa-W756.QX3QDO0wCM4EzNzEzW}
```

### New Learnings
-> You can resume processes in the background with the bg command! This will allow the process to keep running, while giving you your shell back to invoke more commands in the meantime.

### References 
The module instruction was used.



## Challenge 8: Foregrounding Processes
Foregrounding a background process using fg.

### Solve
**Flag:** `pwn.college{EibQs7yNUmXSeXFJ26AqPLh8O85.QX4QDO0wCM4EzNzEzW}`

First, "/challenge/run" was executed and then suspended using "ctrl-z" and then resumed again using "bg /challenge/run" which got executed in the background, enter was pressed to come out. To foreground the process "fg /challenge/run" was used and then enter was pressed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.

hacker@processes~foregrounding-processes:~$ fg /challenge/run
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{EibQs7yNUmXSeXFJ26AqPLh8O85.QX4QDO0wCM4EzNzEzW}
```

### New Learnings
-> you can foreground a backgrounded process with fg just like you foreground a suspended process

### References 
The module instruction was used.



## Challenge 9: Starting Backgrounded Processes
Launching commands backgrounded

### Solve
**Flag:** `pwn.college{kDdINqh5OYbycMBGxnRuun4n1vL.QX5QDO0wCM4EzNzEzW}`

To launch "/challenge/run" backgrounded, "/challenge/run &" was executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run &
[1] 339
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{kDdINqh5OYbycMBGxnRuun4n1vL.QX5QDO0wCM4EzNzEzW}

[1]+  Done                    /challenge/run

```

### New Learnings
->  Suspend processes to background them  is not required; you can start them backgrounded by appending a & to the command

### References 
The module instruction was used.



## Challenge 10: Process Exit Code
This challenge deals with accessing exit codes

### Solve
**Flag:** `pwn.college{YlkFxhnxsVvp8aYrlOkxGuuXBbQ.QX5YDO1wCM4EzNzEzW}`

First, "/challenge/get-code" was executed, then "echo $?" was used to print the exit code onto the terminal. "/challenge/submit-code" was executed with the argument as the exit code. Therefore, "/challenge/submit-code 115" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
115
hacker@processes~process-exit-codes:~$ /challenge/submit-code 115
CORRECT! Here is your flag:
pwn.college{YlkFxhnxsVvp8aYrlOkxGuuXBbQ.QX5YDO1wCM4EzNzEzW}
```

### New Learnings
-> You can access the exit code of the most recently-terminated command using the special ? variable (don't forget to prepend it with $ to read its value)

### References 
The module instruction was used.