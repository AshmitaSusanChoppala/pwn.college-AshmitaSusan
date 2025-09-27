# Practicing Piping

## Challenge 1: Redirecting output
This challenge shows the purpose of redirecting output.

### Solve
**Flag:** `pwn.college{0uquamhiKAjpdZm3ZrsGba-P1aM.QX0YTN0wCM4EzNzEzW}`

We were asked to redirect "PWN" to the file "COLLEGE" which was done using ">" symbol."echo PWN > COLLEGE" was given as the input which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{0uquamhiKAjpdZm3ZrsGba-P1aM.QX0YTN0wCM4EzNzEzW}
```

### New Learnings
-> You can accomplish redirecting stdout to files with the > character

### References 
The module instruction was used.



## Challenge 2: Redirecting more output
More exercise on redirecting

### Solve
**Flag:** `pwn.college{AOfFL5fB_XXXIadXoHdNYqBs0_3.QX1YTN0wCM4EzNzEzW}`

First, we were asked to redirect the output to myflag file which can be done using "/challenge/run > myflag". Then "cat" was used to read the myflag file which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{AOfFL5fB_XXXIadXoHdNYqBs0_3.QX1YTN0wCM4EzNzEzW}
```

### New Learnings
-> Aside from redirecting the output of echo, you can, of course, redirect the output of any command. 

### References 
The module instruction was used.



## Challenge 3: Appending output
Redirecting files in append mode (using ">>")

### Solve
**Flag:** `pwn.college{ww-kSremuNep_ooH4NSg1ym8wWX.QX3ATO0wCM4EzNzEzW}`

First, "/challenge/run >> /home/hacker/the-flag" was run to redirected the output. "cat /home/hacker/the-flag" was usd to read the file which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run >> /home/hacker/the-flag
cat /home/hacker/the-flag
pwn.college{ww-kSremuNep_ooH4NSg1ym8wWX.QX3ATO0wCM4EzNzEzW}
```

### New Learnings
-> '>' will create a new output file every time, deleting the old contents.

### References 
The module instruction was used.



## Challenge 4: Redirecting errors
Using FD to redirect outputs

### Solve
**Flag:** `pwn.college{Yg1I2MdXODiAXDyfidhCWJmkTUX.QX3YTN0wCM4EzNzEzW}`

We were asked to redirect the output of "/challenge/run" to "myflag" and the errors to "instructions". This can can be done using "/challenge/run 1> myflag 2> instructions" as 1> is used to redirect standard output and 2> redirects standard error. Then, "cat instructions" was used to read the instructions in "instructions" file and "cat myflag" was used to read the "myflag" file which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run 1> myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{Yg1I2MdXODiAXDyfidhCWJmkTUX.QX3YTN0wCM4EzNzEzW}
```

### New Learnings
-> A File Descriptor (FD) is a number that describes a communication channel in Linux. 
-> a > without a number implies 1>, which redirects FD 1 (Standard Output).
-> 2> redirects standard error (FD 2) to the errors.log file.

### References 
The module instruction was used.



## Challenge 5: Redirecting input
Using "<" to redirect inputs.

### Solve
**Flag:** `pwn.college{UaDqtd1SiPjuW1esyjvHCosUq-F.QXwcTN0wCM4EzNzEzW}`

We were asked to "echo" the value "COLLEGE" to "PWN" file (which can be done using "echo COLLEGE > PWN") and then redirect the input to "/challenge/run" (By using "/challenge/run < PWN"). This gave flag as the otuput. Then the flag was copied and pasted into the flag box.

```bash
echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{UaDqtd1SiPjuW1esyjvHCosUq-F.QXwcTN0wCM4EzNzEzW}
```

### New Learnings
-> Just like you can redirect output from programs, you can redirect input to programs! This is done using <.

### References 
The module instruction was used.



## Challenge 6: Grepping stored results
Using redirect output and grep commands

### Solve
**Flag:** `pwn.college{s95mIpiRqITVEqrQR66xRVimkrs.QX4EDO0wCM4EzNzEzW}`

We were asked to redirect the output of "/challenge/run" to "/tmp/data.txt", which can be done using "/challenge/run > /tmp/data.txt". Then, we can search for the flag using the grep command, "grep pwn.college /tmp/data.txt". This gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run > /tmp/data.txt
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{s95mIpiRqITVEqrQR66xRVimkrs.QX4EDO0wCM4EzNzEzW}
```

### New Learnings
-> Using commands, redirecting outputs and grep.

### References 
The module instruction was used.



## Challenge 7: Grepping live output
Using the | (pipe) operator

### Solve
**Flag:** `pwn.college{siQ2bzLhBLdiv8_mSrdFEsAT_bf.QX5EDO0wCM4EzNzEzW}`

We were asked to grep for the flag in the output of "/challenge/run". This was done using the pipe operator as "/challenge/run | grep pwn.college", which gave the flag as the output.Then the flag was copied and pasted into the flag box.

```bash
/challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{siQ2bzLhBLdiv8_mSrdFEsAT_bf.QX5EDO0wCM4EzNzEzW}
```

### New Learnings
-> You can avoid the need to store results to a file by using the | (pipe) operator.
-> Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the command to the right of the pipe.

### References 
The module instruction was used.



## Challenge 8: Grepping errors
Using the ">&" operator

### Solve
**Flag:** `pwn.college{kTfgVNhLpyYPhjXcMjlNfnJtfoK.QX1ATO0wCM4EzNzEzW}`

To redirect the standard error to the standard output and then grep for the flag can be done using the ">&" and the "|" operators as so: "/challenge/run 2>& 1 | grep pwn.college", which gave the output as the flag. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run 2>& 1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{kTfgVNhLpyYPhjXcMjlNfnJtfoK.QX1ATO0wCM4EzNzEzW}
```

### New Learnings
-> The | operator redirects only standard output to another program, and there is no 2| form of the operator! It can only redirect standard output (file descriptor 1).
-> The shell has a >& operator, which redirects a file descriptor to another file descriptor.

### References 
The module instruction was used.



## Challenge 9: Filtering with grep -v
Using the "grep -v" command

### Solve
**Flag:** `pwn.college{c1T51D3K_zvxXWb0DavJxtPUe4L.0FOxEzNxwCM4EzNzEzW}`

To redirect the output of "/challenge/run" to stdout and to filter all the lines that do not contain the flag, "|" operator and "grep -v" command was used. "/challenge/run | grep -v DECOY" was given as the input which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run | grep -v DECOY
pwn.college{c1T51D3K_zvxXWb0DavJxtPUe4L.0FOxEzNxwCM4EzNzEzW}
```

### New Learnings
-> The grep command has a very useful option: -v (invert match). While normal grep shows lines that MATCH a pattern, grep -v shows lines that do NOT match a pattern

### References 
The module instruction was used.



## Challenge 10: Duplicating piped data with tee
Using "tee" command 

### Solve
**Flag:** `pwn.college{QIg499WBMhn7l0DFglFTLSH1wNG.QXxITO0wCM4EzNzEzW}`

"tee" command was used to redirect the stdout of "/challenge/pwn" to "/dev/tty"(shows the output to the terminal) and "/challenge/college". Then, "/challenge/pwn --secret QIg499WB 2>&1 | tee ./pwn_data | /challenge/college" was executed based on the clues which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/pwn | tee /dev/tty | /challenge/college
Processing...
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "QIg499WB"
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret QIg499WB 2>&1 | tee ./pwn_data | /challenge/college
Processing...
WARNING: you are overwriting file ./pwn_data with tee's output...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{QIg499WBMhn7l0DFglFTLSH1wNG.QXxITO0wCM4EzNzEzW}
```

### New Learnings
-> The tee command, named after a "T-splitter" from plumbing pipes, duplicates data flowing through your pipes to any number of files provided on the command line.

### References 
The module instruction was used.



## Challenge 11: Process substitution for input
Using diff command and <(command)

### Solve
**Flag:** `pwn.college{cjPRlVK_EBHqjuW8EH6XT3zjPaH.0lNwMDOxwCM4EzNzEzW}`

We were asked to print the difference between "/challenge/print_decoys" and "/challenge/print_decoys_and_flag" to get the flag.We can do this using the "diff" command. "diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)" was given as the input as "/challenge/print_decoys" and "/challenge/print_decoys_and_flag" are commands and are specified using "<(command)" operator. The flag emerged as the putput. Then the flag was copied and pasted into the flag box.

```bash
diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
50a51
> pwn.college{cjPRlVK_EBHqjuW8EH6XT3zjPaH.0lNwMDOxwCM4EzNzEzW}
```

### New Learnings
-> We can hook input and output of programs to arguments of commands. This is done using Process Substitution. 
-> For reading from a command (input process substitution), use <(command). 
-> When you write <(command), bash will run the command and hook up its output to a temporary file that it will create. 

### References 
The module instruction was used.



## Challenge 12: Writing to multiple programs
Using pipe, tee and >(command) operator

### Solve
**Flag:** `pwn.college{A8NvTlVTnfIBv5Jsm7V0EJTIQUz.QXwgDN1wCM4EzNzEzW}`

"|" was used to redirect the standard output from "/challenge/hack" to "/challenge/the" and "/challenge/planet"; "tee" was used to duplicate the output to "/challenge/the" and "/challenge/planet"; ">(command)" was used as "/challenge/the" and "/challenge/planet" are both commands. "/challenge/hack | tee >(/challenge/the) >(/challenge/planet)" was given as the input which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
11913259251802429703
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{A8NvTlVTnfIBv5Jsm7V0EJTIQUz.QXwgDN1wCM4EzNzEzW}
```

### New Learnings
-> Process substitution can make command output appear as files for reading with <(command),  but you can also use process substitution for writing to commands.
-> If you write an argument of >(rev), bash will run the rev command (this command reads data from standard input, reverses its order, and writes it to standard output!), but hook up its input to a temporary named pipe file.

### References 
The module instruction was used.



## Challenge 13: Split-piping stderr and stdout
Redirecting stderr and stdout using "2>" and ">()".

### Solve
**Flag:** `pwn.college{8jE0JZjIZGKDMoK3-kHgatzMSYM.QXxQDM2wCM4EzNzEzW}`

First, the output of "/challenge/hack" is redirected to "/challenge/planet" by using ">" and ">()", and then the stderr of "/challenge/hack" is redirected to "/challenge/the" using "2>" and ">()". "/challenge/hack > >(/challenge/planet) 2> >(/challenge/the)" was given as the input which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/hack > >(/challenge/planet) 2> >(/challenge/the)
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{8jE0JZjIZGKDMoK3-kHgatzMSYM.QXxQDM2wCM4EzNzEzW}
```

### New Learnings
-> Use of previously learnt redirection techniques.

### References 
The module instruction was used.



## Challenge 14: Named pipes
Using "FIFO"s

### Solve
**Flag:** `pwn.college{ArPy9fFwtYSD_fC-T6trAUH3nns.01MzMDOxwCM4EzNzEzW}`

First, a FIFO file was created using "mkfifo" command, "mkfifo /tmp/flag_fifo" given as the input. Then, the output of "/challenge/run" was redirected to "/tmp/flag_fifo". Due to the "blocking" nature of FIFO, it had to be read, so "cat /tmp/flag_fifo" was executed in another terminal, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at 
/tmp/flag_fifo! Here is your flag:
pwn.college{ArPy9fFwtYSD_fC-T6trAUH3nns.01MzMDOxwCM4EzNzEzW}
```

### New Learnings
-> You can also create your own persistent named pipes that stick around on the filesystem! These are called FIFOs, which stands for First (byte) In, First (byte) Out.
-> You create a FIFO using the mkfifo command.
-> the p at the beginning of the permissions - that indicates it's a pipe.
-> One problem with FIFOs is that they'll "block" any operations on them until both the read side of the pipe and the write side of the pipe are ready.

### References 
The module instruction was used.
