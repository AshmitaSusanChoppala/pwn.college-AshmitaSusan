# Terminal Multiplexing

## Challenge 1: Launching Screen
This challenge deals with launching and accessing screen

### Solve
**Flag:** `pwn.college{4hR3Zz4jstFT4EhPofxQkdI5bPT.0VN4IDOxwCM4EzNzEzW}`

To launch a screen session, "screen" was given as the input, then the screen session opened and gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
screen
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{4hR3Zz4jstFT4EhPofxQkdI5bPT.0VN4IDOxwCM4EzNzEzW}
```

### New Learnings
-> screen is a program that creates virtual terminals inside your terminal. It's somewhat like having multiple browser tabs, but for your command line.
-> When you're done with your command line, type exit or press Ctrl-D to leave the screen session. Then screen will terminate and return you to your original shell.

### References 
The module instruction was used.



## Challenge 2: Detaching and Attaching 
This challenge deals with detaching and reattaching shell scripts

### Solve
**Flag:** `pwn.college{MLTl5k2YC-Ws87On2A13UZwts48.0lN4IDOxwCM4EzNzEzW}`

To launch a screen session, "screen" was given as the input. In the screen, To detach from it, ctrl-a the d were pressed. Returned back to the terminal, "/challenge/run" was executed and then to reattach the screen (to get the flag) "screen -r"was given as the input. Then, the screen echoed the output. Then the flag was copied and pasted into the flag box.

```bash
screen
ctrl-a, d
[detached from 340.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 340.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
pwn.college{MLTl5k2YC-Ws87On2A13UZwts48.0lN4IDOxwCM4EzNzEzW}
```

### New Learnings
-> With screen, your work keeps running even when your connection drops, and you can reattach later.
-> You detach by pressing Ctrl-A, followed by d (for detach). This leaves your session running in the background while you return to your normal terminal.
-> To reattach, you can use the -r argument to screen.
-> Ctrl-A is screen's activation key for all of its shortcuts in its default configuration. All screen functionality is activated by some command combination starting with Ctrl-A

### References 
The module instruction was used.



## Challenge 3: Finding Sessions
This challenge deals with finding and reattaching the session required when there are multiple sessions

### Solve
**Flag:** `pwn.college{4GiyBVuyMOJoJSR0qA-Cms3fm1x.01N4IDOxwCM4EzNzEzW}`

First, "screen -ls" was used to list the sessions. There were three sessions that were detached and each of them had to be checked for the flag. To do that, the scrrens had to be reattached, which can be done by using "screen -r [name/PID]". The right session was the one with PID 144 which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash 
screen -ls
There are screens on:
	352.pts-0.terminal-multiplexing~launching-screen	(Remote or dead)
	378.pts-0.terminal-multiplexing~launching-screen	(Remote or dead)
	340.pts-0.terminal-multiplexing~detaching-and-attaching	(Remote or dead)
	144.session_8efc09a43178b25e	(Detached)
	147.session_f274638b7f8ce7bd	(Detached)
	150.session_b4d37302725b36f2	(Detached)
6 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 144
echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{4GiyBVuyMOJoJSR0qA-Cms3fm1x.01N4IDOxwCM4EzNzEzW}
pwn.college{4GiyBVuyMOJoJSR0qA-Cms3fm1x.01N4IDOxwCM4EzNzEzW}
[detached from 144.session_8efc09a43178b25e]
```

### New Learnings
-> The identifiers of the sessions(which are listed by using -ls) are the PID of each respective screen process, a dot, and the name of the screen session. To attach to a specific one, you use its name or its PID by giving it as an argument to screen -r.

### References 
The module instruction was used.



## Challenge 4: Switching Windows
This challenge deals with switching windows using ctrl-A

### Solve
**Flag:** `pwn.college{su-QLkduU9EfynlzewhRnWtonma.0FO4IDOxwCM4EzNzEzW}`

First, screen can be attached using "screen -r". In the screen, the prompt said that we were currently in window 1 and had to switch to window 0 to get the flag. To do that, we need to press ctrl-a then 0. When it was done, it gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
screen -r

cat <<MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Welcome to the window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-A 0 to switch to window 0!
> MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
hacker@terminal-multiplexing~switching-windows:~$ ctrl-a 0

cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{su-QLkduU9EfynlzewhRnWtonma.0FO4IDOxwCM4EzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{su-QLkduU9EfynlzewhRnWtonma.0FO4IDOxwCM4EzNzEzW}
```

### New Learnings
-> These windows are handled with different keyboard shortcuts, all starting with Ctrl-A:
Ctrl-A c - Create a new window
Ctrl-A n - Next window
Ctrl-A p - Previous window
Ctrl-A 0 through Ctrl-A 9 - Jump directly to window 0-9
Ctrl-A " - bring up a selection menu of all of the windows

### References 
The module instruction was used.



## Challenge 5: Detaching and Attaching (tmux)
This challenge deals with detaching and attaching from screen using tmux(ctrl-b)

### Solve
**Flag:** `pwn.college{A7dayRNCgxsdww-89euuNXOPPek.0VO4IDOxwCM4EzNzEzW}`

First, to launch the tmux session, "tmux" was given as the input. To detach from it, we need to press ctrl-b then d. Then, "/challenge/run" was executed which sent the flag to the tmux session. To reattach, "tmux a" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
ctrl-b d
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux a
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{A7dayRNCgxsdww-89euuNXOPPek.0VO4IDOxwCM4EzNzEzW}
Congratulations, here is your flag: pwn.college{A7dayRNCgxsdww-89euuNXOPPek.0VO4IDOxwCM4EzNzEzW}
```

### New Learnings
-> tmux (terminal multiplexer) is screen's younger, more modern cousin. It does all the same things but with some different key bindings. The biggest difference? Instead of Ctrl-A, tmux uses Ctrl-B as its command prefix.
-> to detach from tmux, you press Ctrl-B followed by d
->tmux ls - List sessions
  tmux attach or tmux a - Reattach to session

### References 
The module instruction was used.



## Challenge 6: Switching Windows (tmux)
This challenge deals with switching windows using ctrl-B (tmux)

### Solve
**Flag:** `pwn.college{YrVU-L0WR2oMB5YbRkxQVjLBYlq.0FM5IDOxwCM4EzNzEzW}`

First, to reattach the tmux session, "tmux a" was given as the input. In the session, the prompt said that we were currently in window 1(and it was also given below in a status bar) and had to switch to window 0 to get the flag. To do that, we need to press ctrl-b then 0. When it was done, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
tmux a
cat <<MSG
Welcome to the tmux window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-B 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Welcome to the tmux window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-B 0 to switch to window 0!
> MSG
Welcome to the tmux window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-B 0 to switch to window 0!
ctrl-b 0
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{YrVU-L0WR2oMB5YbRkxQVjLBYlq.0FM5IDOxwCM4EzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{YrVU-L0WR2oMB5YbRkxQVjLBYlq.0FM5IDOxwCM4EzNzEzW}
```

### New Learnings
-> tmux has windows, just like screen. The key combos are different, but the concept is the same:
Ctrl-B c - Create a new window
Ctrl-B n - Next window
Ctrl-B p - Previous window
Ctrl-B 0 through Ctrl-B 9 - Jump to window 0-9
Ctrl-B w - See a nice window picker

### References 
The module instruction was used.