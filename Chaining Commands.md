# Chaining Commands

## Challenge 1: Chaining with Semicolons
Running commands using chaining(;)

### Solve
**Flag:** `pwn.college{kIaDZhO-MRik1cdYVW39PQg6D1a.QX1UDO0wCM4EzNzEzW}`

To run "/challenge/pwn" and "/challenge/college" chained with ";", "/challenge/pwn; /challenge/college" must be given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{kIaDZhO-MRik1cdYVW39PQg6D1a.QX1UDO0wCM4EzNzEzW}
```

### New Learnings
-> The easiest way to chain commands is ;

### References 
The module instruction was used.



## Challenge 2: Buiding on Success 
This challenge deals with chaining using "&&" operator

### Solve
**Flag:** `pwn.college{UcFyuHXpuxfoyUbkHPWqd8PJHqk.0lM0MDOxwCM4EzNzEzW}`

To chain the programs "/challenge/first-success" and "/challenge/second" using "&&", "/challenge/first-success && /challenge/second" must be given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/first-success
hacker@chaining~building-on-success:~$ /challenge/second
Error: /challenge/first-success must be successfully chained with 
/challenge/second using &&
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{UcFyuHXpuxfoyUbkHPWqd8PJHqk.0lM0MDOxwCM4EzNzEzW}
```

### New Learnings
-> The && operator allows you to run a second command only if the first command succeeds (in Linux convention, this means it exited with code 0). This is called the "AND" operator because both conditions must be true: the first command must succeed AND then the second command will run.
-> Syntax:
hacker@dojo:~$ command1 && command2
This means: "Run command1, and IF it succeeds, then run command2."
-> The || operator is super useful for providing fallback commands or error handling

### References 
The module instruction was used.



## Challenge 3: Handling Failure 
This challenge deals with chaining using "||" operator

### Solve
**Flag:** `pwn.college{EfW3VGGhADIRrNh2VZFQMNsRlYe.01M0MDOxwCM4EzNzEzW}`

To chain the programs "/challenge/first-success" and "/challenge/second" using "&&", "/challenge/first-success && /challenge/second" must be given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{EfW3VGGhADIRrNh2VZFQMNsRlYe.01M0MDOxwCM4EzNzEzW}
```

### New Learnings
-> The || operator allows you to run a second command only if the first command fails (exits with a non-zero code). This is called the "OR" operator because either the first command succeeds OR the second command will run.
-> Syntax:
hacker@dojo:~$ command1 || command2
This means: "Run command1, and IF it fails, then run command2."

### References 
The module instruction was used.



## Challenge 4: Your First Shell Script 
Creating and executing several commands using shell script

### Solve
**Flag:** `pwn.college{QBisvOhdVqk9iigPr5Scd6bxTzY.QXxcDO0wCM4EzNzEzW}`

First, the shell script named "x.sh" was created using a text editor. The shell script had the commands "/challenge/pwn" and "/challenge/college". Then, it was executed by giving "bash x.sh" as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
x.sh-
/challenge/pwn
/challenge/college

bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{QBisvOhdVqk9iigPr5Scd6bxTzY.QXxcDO0wCM4EzNzEzW}
```

### New Learnings
-> As you combine more and more commands to achieve complex effects, the length of the combined prompt quickly gets really annoying to deal with. When this happens, you can put these commands in a file, called a shell script, and run them by executing the file.
-> shell scripts are frequently named with a sh suffix.
-> It can be executed by passing the shell script as an argument to a new instance of the shell (bash).

### References 
The module instruction was used.



## Challenge 5: Redirecting Script Output
Using piping to to send/redirect the output of several programs to one command.

### Solve
**Flag:** `pwn.college{8rXZsMy5MxwIkz9VD0-KqS2qJng.QX4ETO0wCM4EzNzEzW}`

First, the shell script named "x.sh" was created using a text editor. The shell script had the commands "/challenge/pwn" and "/challenge/college". Then, the output of shell script is piped as the input to "/challenge/solve" program, by giving "bash x.sh | /challenge/solve" as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
x.sh-
/challenge/pwn
/challenge/college

bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{8rXZsMy5MxwIkz9VD0-KqS2qJng.QX4ETO0wCM4EzNzEzW}
```

### New Learnings
-> All of the various redirection methods work: > for stdout, 2> for stderr, < for stdin, >> and 2>> for append-mode redirection, >& for redirecting to other file descriptors, and | for piping to another command to redirect script output.

### References 
The module instruction was used.



## Challenge 6: Executable Shell Scripts
Invoking shell scripts using their relative/absolute path.

### Solve
**Flag:** `pwn.college{gBR1Udpf05HmRJ1Ozzg_tcmksKh.QX0cjM1wCM4EzNzEzW}`

First, a shell script named "script.sh" was created using a text editor. The shell script had the command "/challenge/solve". To enable permissions, "chmod a+x /home/hacker/script.sh" was executed. Then, the shell script was invoked using absolute path as "/home/hacker/script.sh", which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
script.sh -
/challenge/solve

chmod a+x /home/hacker/script.sh
hacker@chaining~executable-shell-scripts:~$ /home/hacker/script.sh
Congratulations on your shell script execution! Your flag:
pwn.college{gBR1Udpf05HmRJ1Ozzg_tcmksKh.QX0cjM1wCM4EzNzEzW}
```

### New Learnings
->  If your shell script file is executable (recall File Permissions), you can simply invoke it via its relative or absolute path

### References 
The module instruction was used.



## Challenge 7: Understanding Shebangs
Executing programs using shebangs

### Solve
**Flag:** `pwn.college{k8XqNOlTcFFwWprJtbK-UL_lGL_.0VOzMDOxwCM4EzNzEzW}`

First, a shell script named "solve.sh" was created using a text editor. The shell script had to be created using shebangs "#!/bin/bash" amd should execute "echo "hack the planet"". To enable permissions, "chmod a+x /home/hacker/script.sh" was executed.Then, "/challenge/run" was executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
solve.sh-
#!/bin/bash

echo "hack the planet"

chmod a+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{k8XqNOlTcFFwWprJtbK-UL_lGL_.0VOzMDOxwCM4EzNzEzW}
```

### New Learnings
-> if the program file starts with the characters #! (often termed a "shebang"), Linux treats the file as an interpreted program, and the contents of the rest of the line as the path to the interpreter. It then invokes the interpreter with the path to the program file as its only argument.
-> Common shebangs you might see:
#!/bin/bash for bash scripts
#!/usr/bin/python3 for Python scripts
#!/bin/sh for POSIX shell scripts --- this is a more primitive predecessor to bash with fewer features, but more compatibility to non-Linux systems!

### References 
The module instruction was used.



## Challenge 8: Scripting with Arguments 
Using shell scripts with arguments

### Solve
**Flag:** `pwn.college{UGZVFBcOpsgN9F8fs3CEDxYsPbf.0VNzMDOxwCM4EzNzEzW}`

First, a shell script named "solve.sh" was created using a text editor. The shell script was created using shebangs "#!/bin/bash" and since second argument should be the first output and first argument the second "echo "$2 $1"" was written into the file. In the terminal, the shell script was called with an argument as "bash solve.sh pwn college". Then, "/challenge/run" was executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
solve.sh-
#!/bin/bash

echo "$2 $1"
bash solve.sh pwn college
college pwn
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{UGZVFBcOpsgN9F8fs3CEDxYsPbf.0VNzMDOxwCM4EzNzEzW}
```

### New Learnings
-> The script can access arguments using special variables:
$1 contains the first argument ("hello")
$2 contains the second argument ("world")
$3 would contain the third argument (if there had been one)
...and so on

### References 
The module instruction was used.



## Challenge 9: Scripting with Conditionals
Scripting using if conditional statement

### Solve
**Flag:** `pwn.college{0GjdTOF7PYKMQZCofnfetgQ3oRs.0lNzMDOxwCM4EzNzEzW}`

First, a shell script named "solve.sh" was created using a text editor. The shell script was created using shebangs "#!/bin/bash" and conditional statements. The conditional statement was that if the argument to the shell script was "pwn" then "college" would be the output, else, no output. In the terminal, the shell script was called with an argument as "bash /home/hacker/solve.sh pwn" which gave the output as college. Then, "/challenge/run" was executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
solve -sh
#!/bin/bash

if [ "$1" == "pwn" ]
then
    echo "college"
fi

bash /home/hacker/solve.sh pwn
college
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{0GjdTOF7PYKMQZCofnfetgQ3oRs.0lNzMDOxwCM4EzNzEzW}
```

### New Learnings
-> First, you must have spaces after if (if you're used to a language like C, this is different), after [, and before ]. Second, if, then, and fi must all be on different lines (or separated by semicolons); you can't lump them into the same statement. It's also a bit weird: instead of endif or end or something like that, the terminator of the if statement is fi (if backwards). 

### References 
The module instruction was used.



## Challenge 10: Scripting with Default Cases
Scripting using if-else conditional statement

### Solve
**Flag:** `pwn.college{MH1090xpiVMo2BJGDtf8U9cHGkj.01NzMDOxwCM4EzNzEzW}`

First, a shell script named "solve.sh" was created using a text editor. The shell script was created using shebangs "#!/bin/bash" and conditional statements. The conditional statement was that if the argument to the shell script was "pwn" then "college" would be the output, else, the output is "nope". In the terminal, the shell script was called with an argument as "bash /home/hacker/solve.sh pwn" which gave the output as "college". The shell script was again called with an argument as "bash /home/hacker/solve.sh hack" which gave the output as "hack".  Then, "/challenge/run" was executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
solve.sh-
#!/bin/bash

if [ "$1" == "pwn" ]
then
    echo "college"
else 
    echo "nope"
fi

bash /home/hacker/solve.sh pwn
college
hacker@chaining~scripting-with-default-cases:~$ bash /home/hacker/solve.sh hack
nope
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{MH1090xpiVMo2BJGDtf8U9cHGkj.01NzMDOxwCM4EzNzEzW}
```

### New Learnings
-> The else clause executes when the if condition is false
   Note that the else doesn't have a condition --- it catches everything that didn't match previously. It also doesn't have a then statement. Finally, the fi goes after the else block to denote the end of the whole complex statement

### References 
The module instruction was used.



## Challenge 11: Scripting with Multiple Conditions
Scripting in the case of multiple conditions (using elif)

### Solve
**Flag:** `pwn.college{w8JhZHoIrUr10fhCDxtlQR7tcBb.0FOzMDOxwCM4EzNzEzW}`

First, a shell script named "solve.sh" was created using a text editor. The shell script was created using shebangs "#!/bin/bash" and multiple conditional statements. The conditional statements should be specified by elif. The first conditional statement was that if the argument to the shell script was "hack" then "the planet" would be the output;  second conditional statement was that if the argument was "pwn" then "college" would be the output; third conditional statement was that if the argument to the shell script was "learn" then "linux" would be the output; else(when none of the conditions satisfy), the output is "unknown". In the terminal, the shell script was called with arguments being hack/pwn/learn/dojo as "bash /home/hacker/solve.sh[argument]" which gave the output as "the planet/college/linux/unknown".  Then, "/challenge/run" was executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
solve.sh-
#!/bin/bash

if [ "$1" == "hack" ]
then
       echo "the planet"
elif [ "$1" == "pwn" ]
then
       echo "college"
elif [ "$1" == "learn" ] 
then      
       echo "linux"
else
       echo "unknown"
fi     

bash /home/hacker/solve.sh hack
the planet
hacker@chaining~scripting-with-multiple-conditions:~$ bash /home/hacker/solve.sh pwn
college
hacker@chaining~scripting-with-multiple-conditions:~$ bash /home/hacker/solve.sh learn
linux
hacker@chaining~scripting-with-multiple-conditions:~$ bash /home/hacker/solve.sh dojo
unknown
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{w8JhZHoIrUr10fhCDxtlQR7tcBb.0FOzMDOxwCM4EzNzEzW}
```

### New Learnings
-> elif is used for checking multiple conditions
-> Note that you do need a then after the elif, just like the if. As before the else at the end catches everything that didn't match.

### References 
The module instruction was used.



## Challenge 12: Reading Shell Scripts
This challenge deals with reading shell scripts

### Solve
**Flag:** `pwn.college{gRuLFIp9M39-yoAVfD8GfofuCBA.0lMwgDOxwCM4EzNzEzW}`

First, the shell script "/challenge/run" was read using cat. The shell script said that if GUESS is "hack the PLANET", the flag would be given. Therefore, "/challenge/run" was executed and "hack the PLANET" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
	echo "CORRECT! Your flag:"
	cat /flag
else
	echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET
CORRECT! Your flag:
pwn.college{gRuLFIp9M39-yoAVfD8GfofuCBA.0lMwgDOxwCM4EzNzEzW}
```

### New Learnings
-> reading shell scripts

### References 
The module instruction was used.