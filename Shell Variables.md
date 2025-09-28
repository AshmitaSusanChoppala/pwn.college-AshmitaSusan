# Shell Variables

## Challenge 1: Printing Variables
This challenge deals with printing variables

### Solve
**Flag:** `pwn.college{oyo9H-TpR08YUUoCMQA-xqah-v1.QX3UTN0wCM4EzNzEzW}`

To print the variable "echo $" is used. To print the flag, "echo $FLAG" was given as the input which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
echo $FLAG
pwn.college{oyo9H-TpR08YUUoCMQA-xqah-v1.QX3UTN0wCM4EzNzEzW}
```

### New Learnings
-> You can also print out variables with echo, by prepending the variable name with a $. 

### References 
The module instruction was used.



## Challenge 2: Setting Variables
This challenge deals with assigning values to variables.

### Solve
**Flag:** `pwn.college{E_fly7PBjV1G_xry6Aa4zuXNtXk.QX5UTN0wCM4EzNzEzW}`

We were asked to assign COLLEGE to PWN which can be done using "=". So, "PWN=COLLEGE" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{E_fly7PBjV1G_xry6Aa4zuXNtXk.QX5UTN0wCM4EzNzEzW}
```

### New Learnings
-> You can write values to variables, this is done, as with many other languages, using =.
-> There are no spaces around the =.

### References 
The module instruction was used.



## Challenge 3: Multi-word Variables
This challenge deals with assigning mutliple words to variables

### Solve
**Flag:** `pwn.college{470RlO69ZYx_i7HpyUbSgyX7FgU.QXwYTN0wCM4EzNzEzW}`

We were asked to assign COLLEGE YEAH to PWN which can be done using "=" and quoting. So, "PWN="COLLEGE YEAH"" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{470RlO69ZYx_i7HpyUbSgyX7FgU.QXwYTN0wCM4EzNzEzW}
```

### New Learnings
-> To assign mutliple words to variables, we need to quote it, this is known as quoting.

### References 
The module instruction was used.



## Challenge 4: Exporting Variables
This challenge deals with exporting variables

### Solve
**Flag:** `pwn.college{8s1Smg1MT_CtrrRxxUi4OSyb28D.QXyYTN0wCM4EzNzEzW}`

We were asked to export the PWN variable and set it to the value COLLEGE which can be done by giving "export PWN=COLLEGE" as the input. The COLLEGE variable should be set to the value PWN which can be done by "COLLEGE=PWN". Then "sh" is called and "/challenge/run" is executed, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ sh
sh-5.2$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{8s1Smg1MT_CtrrRxxUi4OSyb28D.QXyYTN0wCM4EzNzEzW}
```

### New Learnings
-> The $ prompt is the prompt of sh, a minimal shell implementation that is invoked as a child of the main shell process.
-> When you export your variables, they are passed into the environment variables of child processes. 

### References 
The module instruction was used.



## Challenge 5: Printing Exported Variables
This challenge deals with the use and implementation of "env" command

### Solve
**Flag:** `pwn.college{ks-CP0GCE2guvBKAzHzu56FHstp.QX4UTN0wCM4EzNzEzW}`

"env" was used to print out every exported variable set and it's output is given to the grep command which is used to find the flag. Combined,"env | grep FLAG" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
env | grep FLAG
FLAG=pwn.college{ks-CP0GCE2guvBKAzHzu56FHstp.QX4UTN0wCM4EzNzEzW}
```

### New Learnings
-> env command: It'll print out every exported variable set in the shell.

### References 
The module instruction was used.



## Challenge 6: Storing Command Output
This challenge deals with the use and implementation of command substitution.

### Solve
**Flag:** `pwn.college{4Bc8sADIyF2zWOCKI8H4gohDUtX.QX1cDN1wCM4EzNzEzW}`

First, we were asked to store the output of the command "/challenge/run" into the variable "PWN", this can be done using command substitution as "PWN=$(/challenge/run)". Then to read the variable, "echo "$PWN"" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo "$PWN"
pwn.college{4Bc8sADIyF2zWOCKI8H4gohDUtX.QX1cDN1wCM4EzNzEzW}
```

### New Learnings
-> Command Substitution: used for storing the output of a command into a variable.
-> After command substitution, when reading the variable using echo, the argument should be given as "$variable_name".

### References 
The module instruction was used.



## Challenge 7: Reading Input
This challenge deals with reading/taking input from the user.

### Solve
**Flag:** `pwn.college{weIidBTjStztn3n8lXEVud_1zIf.QX4cTN0wCM4EzNzEzW}`

We have to input COLLEGE value to PWN variable using user input. This can be done using read command as so: "read -p "INPUT: " PWN". Then, COLLEGE was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box. (Or, you can also simply just use read PWN and give input directly as COLLEGE).

```bash
read -p "INPUT: " PWN
INPUT: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{weIidBTjStztn3n8lXEVud_1zIf.QX4cTN0wCM4EzNzEzW}
```

### New Learnings
-> read: reads input into a variable
-> The -p argument lets you specify a prompt.

### References 
The module instruction was used.



## Challenge 8: Reading Files
This challenge deals with the combined use of "read" and "<(command)"(redirecting command) instead of command substitution.

### Solve
**Flag:** `pwn.college{4hKsJbbDZPQjDTnUOclY0Xiwnnw.QXwIDO0wCM4EzNzEzW}`

We were asked to read the "/challenge/read_me" file into the PWN environment variable. For that, first, we need to redirect the "/challenge/read_me" into the standard input of read, and so when read reads into PWN, it reads from the file. So, "read PWN < /challenge/read_me" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4hKsJbbDZPQjDTnUOclY0Xiwnnw.QXwIDO0wCM4EzNzEzW}
```

### New Learnings
-> application of the already learnt read command and redirection of command.

### References 
The module instruction was used.