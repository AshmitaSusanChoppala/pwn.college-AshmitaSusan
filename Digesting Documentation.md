# Digesting Documentation

## Challenge 1: Learning From Documentation
This challenge tells about the correct usage of arguments for commands.

### Solve
**Flag:** `pwn.college{YOsUYI4k9I8J9TCTlEJKnB3f7gW.QX0ITO0wCM4EzNzEzW}`

We were given that our program is /challenge/challenge and the argument to be used is --giveflag. So combining these two, we get "/challenge/challenge --giveflag" as the input which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{YOsUYI4k9I8J9TCTlEJKnB3f7gW.QX0ITO0wCM4EzNzEzW}
```

### New Learnings
-> The correct usage of programs depends, in a large part, on the proper specification of arguments to them.

### References 
The module instruction was used.



## Challenge 2: Learning Complex Usage
This challenge uses arguments to arguments to access the flag

### Solve
**Flag:** `pwn.college{EVVVXptnIFf4ZrujCXf3egA4POV.QX1ITO0wCM4EzNzEzW}`

We were given that our program is /challenge/challenge and the argument to be used is --printfile when combined gives the path for the flag. To run the flag file, which is in the root directory, "/challenge/challenge --printfile /flag" was given as the input which gave flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{EVVVXptnIFf4ZrujCXf3egA4POV.QX1ITO0wCM4EzNzEzW}
```

### New Learnings
-> Linux commands can have arguments to their arguments.

### References 
The module instruction was used.



## Challenge 3: Reading Manuals
This challenge tells the usage and implementation of man command.

### Solve
**Flag:** `pwn.college{o1P9mgN7c5SX7qoF8SaYSV0harZ.QX0EDO0wCM4EzNzEzW}`

First, we were asked to read the manual for challenge which can be accessed by "man challenge" command. In the description of the manual, the argument --omgcqo NUM was given which executed the flag only when the number was 197. So, combined with the program given, "/challenge/challenge --omgcqo 197" was given as the input which gave flag as the output. Then the flag was copied and pasted into the flag box.

```bash
man challenge
/challenge/challenge --omgcqo 197
Correct usage! Your flag: pwn.college{o1P9mgN7c5SX7qoF8SaYSV0harZ.QX0EDO0wCM4EzNzEzW}
```

### New Learnings
-> The command man is short for manual, and will display (if available) the manual of the command you pass as an argument. 
-> You can scroll around the manpage with your arrow keys and PgUp/PgDn. When you're done reading the manpage, you can hit q to quit.
-> Manpages are stored in a centralized database, which lives in the /usr/share/man directory, but you never need to interact with it directly: you just query it using the man command.

### References 
The module instruction was used.



## Challenge 4: Searching Manuals
This challenge tells about the ways to search for manuals.

### Solve
**Flag:** `pwn.college{4FlnXZUuhoeUmGwZggpN_dGvqbU.QX1EDO0wCM4EzNzEzW}`

First, we were asked to read the manual for challenge which can be accessed by "man challenge" command. In the description of the manual, the argument for the flag was searched by using "/flag", which led to the argument "--vbtszs" which executed the flag. So, combined with the program given, "/challenge/challenge --vbtszs" was given as the input which gave flag as the output.Then the flag was copied and pasted into the flag box.

```bash
man challenge
/challenge/challenge --vbtszs
Initializing...
Correct usage! Your flag: pwn.college{4FlnXZUuhoeUmGwZggpN_dGvqbU.QX1EDO0wCM4EzNzEzW}
```

### New Learnings
-> You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. 
-> After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards.

### References 
The module instruction was used.



## Challenge 5: Searching for Manuals
Challenge on the man command

### Solve
**Flag:** `pwn.college{QKjauzku07_Q0Sr7s7S-xrDuIPu.QX2EDO0wCM4EzNzEzW}`

First, we were asked to read the manual man which can be accessed using "man man" command. Challenge is searched in the manual using "man -k challenge" command which gave the output as "jauzkursxr (1)       - print the flag!". The new given manual was opened using the man command.In the description of this manual, the argument --jauzku NUM was given which executed the flag only when the number was 070. So, combined with the program given, "/challenge/challenge --jauzku 070" was given as the input which gave flag as the output. Then the flag was copied and pasted into the flag box.

```bash
man man
man -k challenge
jauzkursxr (1)       - print the flag!
man jauzkursxr 
/challenge/challenge --jauzku 070
Correct usage! Your flag: pwn.college{QKjauzku07_Q0Sr7s7S-xrDuIPu.QX2EDO0wCM4EzNzEzW}
```

### New Learnings
-> searching and using a manual.

### References 
The module instruction was used.



## Challenge 6: Helpful Programs
This challenge shows how to access manual without man command

### Solve
**Flag:** `pwn.college{gfT6Gas26fxoCdZl_wO4ejSTgB7.QX3IDO0wCM4EzNzEzW}`

First, I used the "/challenge/challenge --help" to access the manual. The manual was given as shown below. Then,"/challenge/challenge -p" was given to get the secret value which is 626 which was then used in the input as "/challenge/challenge -g 626" which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v]
                                           [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give
                        you the flag
/challenge/challenge -p
The secret value is: 626
/challenge/challenge -g 626
Correct usage! Your flag: pwn.college{gfT6Gas26fxoCdZl_wO4ejSTgB7.QX3IDO0wCM4EzNzEzW}
```

### New Learnings
-> accessing manual without using man command and using arguments.

### References 
The module instruction was used.



## Challenge 7: Help for Builtins
This challenge tells the usage and implementation of builtins.

### Solve
**Flag:** `pwn.college{8Z10PU6qCQ_llS5kmzxCUJ7IAiq.QX0ETO0wCM4EzNzEzW}`

Here, challenge is a builtin not a program and can be accessed using help. The input is given as "help challenge" and the challenge shell is displayed. The argument is given as "--secret VALUE" where the value is given as "8Z10PU6q". Then the input is given as "challenge --secret 8Z10PU6q" which gave flag as the output. Then the flag was copied and pasted into the flag box.

```bash
help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "8Z10PU6q".
challenge --secret 8Z10PU6q
Correct! Here is your flag!
pwn.college{8Z10PU6qCQ_llS5kmzxCUJ7IAiq.QX0ETO0wCM4EzNzEzW}
```

### New Learnings
-> Some commands, rather than being programs with man pages and help options, are built into the shell itself. These are called builtins. 
-> Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs.
-> You can get a list of shell builtins by running the builtin help.
-> You can get help on a specific one by passing it to the help builtin. 

### References 
The module instruction was used.