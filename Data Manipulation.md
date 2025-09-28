# Data Manipulation

## Challenge 1: Translating characters
This challenge deals with the use and implementation of "tr" command.

### Solve
**Flag:** `pwn.college{48hVrK3UGEvE4bmaUeB1tody4S1.01MxEzNxwCM4EzNzEzW}`

To convert lower to upper case and upper to lower case "'a-zA-Z' 'A-Za-z'" was used with the "tr" command. The output of "/challenge/run" was given to the "tr" command. "/challenge/run | tr 'a-zA-Z' 'A-Za-z'" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run | tr 'a-zA-Z' 'A-Za-z'
yOUR CASE-SWAPPED FLAG:
pwn.college{48hVrK3UGEvE4bmaUeB1tody4S1.01MxEzNxwCM4EzNzEzW}
```

### New Learnings
-> One of the purposes of piping data is to modify it.
-> "tr" translates characters it receives over standard input and prints them to standard output. 
-> tr translates the character provided in its first argument to the character provided in its second argument. It can also handle multiple characters

### References 
The module instruction was used.
https://stackoverflow.com/questions/23178769/unix-tr-command-to-convert-lower-case-to-upper-and-upper-to-lower-case



## Challenge 2: Deleting characters
This challenge deals with the deletion of characters using "tr" command with "-d" flag.

### Solve
**Flag:** `pwn.college{YKTHq7YnPZUhChbkWFhuUCSRtVX.0FNxEzNxwCM4EzNzEzW}`

To delete the characters "^%" we can use the "tr" command with the "-d" flag. The output of "/challenge/run" is given as the input to the "tr -d" command. Combining this, "/challenge/run | tr -d ^%" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{YKTHq7YnPZUhChbkWFhuUCSRtVX.0FNxEzNxwCM4EzNzEzW}
```

### New Learnings
-> tr can also translate characters to nothing, this is done via a -d flag and an argument of what characters to delete.

### References 
The module instruction was used.



## Challenge 3: Deleting newlines
This challenge deals with the deletion of newlines.

### Solve
**Flag:** `pwn.college{kOTQJkVPWcEotFmM7fEGeR61KRP.0VNxEzNxwCM4EzNzEzW}`

To delete the newlines(\n), we can use the "tr" command with the "-d" flag. The output of "/challenge/run" is given as the input to the "tr -d" command. Combining this, "/challenge/run | tr -d "\n"" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run | tr -d "\n"
Your line-split flag: pwn.college{kOTQJkVPWcEotFmM7fEGeR61KRP.0VNxEzNxwCM4EzNzEzW}
```

### New Learnings
-> \n is a standin for newline, and it must be in quotes to prevent the shell interpreter itself from trying to interpret it

### References 
The module instruction was used.



## Challenge 4: Extracting the first lines with head
This challenge deals with the use and implementation of head command.

### Solve
**Flag:** `pwn.college{Y8SeWwCtskYGpczWZAiRi7YhT3d.0lNxEzNxwCM4EzNzEzW}`

First, we pipe the output of "/challenge/pwn" and print the first 7 lines of the output using "head -n 7", which is then piped to "/challenge/college". Combining this, "/challenge/pwn | head -n 7 | /challenge/college" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{Y8SeWwCtskYGpczWZAiRi7YhT3d.0lNxEzNxwCM4EzNzEzW}
```

### New Learnings
-> The head command is used to display the first few lines of its input

### References 
The module instruction was used.



## Challenge 5: Extracting specific sections of text
This challenge deals with the use and implementation of cut command.

### Solve
**Flag:** `pwn.college{A4Du1e5IVtQStP42YJv8_VsM4SI.01NxEzNxwCM4EzNzEzW}`

First, "/challenge/run" was run to find out about the column number. Then, the output of "/challenge/run" was piped to "cut -d " " -f2" which extracted the second column (as second column has the flag) and then piped to "tr -d "\n"" to eliminat new lines. Combining this, "/challenge/run | cut -d " " -f2 | tr -d "\n"" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
/challenge/run | cut -d " " -f2 | tr -d "\n"
pwn.college{A4Du1e5IVtQStP42YJv8_VsM4SI.01NxEzNxwCM4EzNzEzW}
```

### New Learnings
-> cut command: used to grab specific columns of data.
-> The -d argument specifies the column delimiter (how columns are separated).
-> The -f argument specifies the field number.

### References 
The module instruction was used.



## Challenge 6: Sorting data
This challenge deals with the use and implementation of sort command.

### Solve
**Flag:** `pwn.college{Il61oCwKhT7e-yAOF1lSA4rpM0B.0FM0MDOxwCM4EzNzEzW}`

To sort the file "/challenge/flags.txt" and since the flag is at the end, we can use "-r" and to get the unique flag, we can use "-u". Combining this, "sort -r -u /challenge/flags.txt" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
sort -r -u /challenge/flags.txt
pwn.college{Il61oCwKhT7e-yAOF1lSA4rpM0B.0FM0MDOxwCM4EzNzEzW}
```

### New Learnings
-> The sort command helps you organize data. 
-> It reads lines from input (or files) and outputs them in sorted order
-> By default, sort orders lines alphabetically. Arguments can change this:
-r: reverse order (Z to A)
-n: numeric sort (for numbers)
-u: unique lines only (remove duplicates)
-R: random order!

### References 
The module instruction was used.