# Comprehending Commands

## Challenge 1: cat: not the pet, but the command
This challenge tells about the significance of the cat command.

### Solve
**Flag:** `pwn.college{gFQ03t__X9_aV4B0bRw6ywNmRHQ.QXxcTN0wCM4EzNzEzW}`

This challenge makes us use the cat command which is used for reading. The input is given as "cat flag" in the terminal as it was given to read the flag using the cat command. The output is the flag. Then the flag was copied and pasted into the flag box.

```bash
cat flag
pwn.college{gFQ03t__X9_aV4B0bRw6ywNmRHQ.QXxcTN0wCM4EzNzEzW}
```

### New Learnings
-> cat command is most often used for reading out files.
-> cat will concatenate multiple files if provided multiple arguments.

### References 
The module instruction was used.



## Challenge 2: catting absolute paths
This challenge shows how absolute paths can be the cat command's argument.

### Solve
**Flag:** `pwn.college{gQcxHBXmoqXEe5l8mCd3VSsC9lv.QX5ETO0wCM4EzNzEzW}`

This challenge makes us the absolute paths as arguments for the cat command. Since, the argument is an absolute path, "/flag" was given as the argument to read the flag. Therefore, the input "cat /flag" was given as the input. The output is the flag. Then the flag was copied and pasted into the flag box.


```bash
cat /flag
pwn.college{gQcxHBXmoqXEe5l8mCd3VSsC9lv.QX5ETO0wCM4EzNzEzW}
```

### New Learnings
-> We can specify cat's arguments as absolute paths.

### References 
The module instruction was used.



## Challenge 3: more catting practice 
This challenge gives more practice using cat command, accessing flag using cat command and absolute paths and not using cd for the file path.

### Solve
**Flag:** `pwn.college{EEerCCDBQSSXUj9U-Jj9FrHau6d.QXwITO0wCM4EzNzEzW}`

This challenge makes us the absolute paths as arguments for the cat command.  "/lib/llvm-10/share/flag" was given as the argument(absolute path) to read the flag. Therefore, the input "cat /lib/llvm-10/share/flag" was given as the input. The output is the flag. Then the flag was copied and pasted into the flag box.

```bash
cat /lib/llvm-10/share/flag
pwn.college{EEerCCDBQSSXUj9U-Jj9FrHau6d.QXwITO0wCM4EzNzEzW}
```

### New Learnings
-> We can use absolute paths as arguments.

### References 
The module instruction was used.



## Challenge 4: grepping for a needle in a haystack
This challenge tells the usage and implementation of grep command.

### Solve
**Flag:** `pwn.college{oJX9JDAdkYHFcIN4J4g3P2RuWA0.QX3EDO0wCM4EzNzEzW}`

This challenge makes us use the grep command to search through a huge text file (for example, the file given has hundred thousand lines of text). In the example given. the syntax of a grep command was given as "grep SEARCH_STRING /path/to/file". Using this, the SEARCH_STRING to be found is "pwn.college" and the path to file is given as "/challenge/data.txt". Putting them together, giving "grep pwn.college /challenge/data.txt" as the input gives flag as the output. Then the flag was copied and pasted into the flag box.

```bash
grep pwn.college /challenge/data.txt
pwn.college{oJX9JDAdkYHFcIN4J4g3P2RuWA0.QX3EDO0wCM4EzNzEzW}
```

### New Learnings
-> If the files are too big to cat out, we use grep command.

### References 
The module instruction was used.



## Challenge 5: comparing files
This challenge tells the usage and implementation of diff command.

### Solve
**Flag:** `pwn.college{E5XysK81-Ck49qUe_wFSTj4QZCF.01MwMDOxwCM4EzNzEzW}`

This challenge makes us the use the diff command to find the difference between two files. The file "/challenge/decoys_only.txt" has 100 fake flags. The file "/challenge/decoys_and_real.txt" has 100 fake flags and the real flag. The difference between the two files is the real flag which can be found easily, without having to go through each flag,by the diff command. "diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt" is given as the input which gave 34a35 (meaning there is an additional line (after line 34 of file1, add line 35 of file2)) and flag as the output. Then the flag was copied and pasted into the flag box.

```bash
diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
34a35
> pwn.college{E5XysK81-Ck49qUe_wFSTj4QZCF.01MwMDOxwCM4EzNzEzW}
```

### New Learnings
-> diff compares two files line by line and shows you exactly what's different between them.
-> c between two numbers(same) means the line (number) has changed.
-> a between two numbers means additional line(after line number1 of file1, add line number2 of file2)

### References 
The module instruction was used.



## Challenge 6: listing files 
This challenge tells the usage and implementation of ls command.

### Solve
**Flag:** `pwn.college{c2bWeNy2E78B4IKu5awH-1pOf6x.QX4IDO0wCM4EzNzEzW}`

This challenge makes us use the ls command to list all the files in the directory. Here, we used ls to list the files in challenge by using "ls /challenge" to find the name of the changed file. "29777-renamed-run-30610  DESCRIPTION.md" was given as the output. By using "/challenge/29777-renamed-run-30610  DESCRIPTION.md" as the input gave the output as the flag.
Then the flag was copied and pasted into the flag box. 

```bash
ls /challenge
29777-renamed-run-30610  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/29777-renamed-run-30610  DESCRIPTION.md
Yahaha, you found me! Here is your flag:
pwn.college{c2bWeNy2E78B4IKu5awH-1pOf6x.QX4IDO0wCM4EzNzEzW}
```

### New Learnings
-> ls command helps to list the files.
-> ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided.

### References 
The module instruction was used.



## Challenge 7: touching files 
This challenge tells the usage and implementation of touch command.

### Solve
**Flag:** `pwn.college{EE0ddeE5-zJgkpaU6reTmW-BA7Q.QXwMDO0wCM4EzNzEzW}`

This challenge makes use of the touch command to create blank files. First we were supposed to create two files "/tmp/pwn" and "/tmp/college" using touch command and then give the input as "/challenge/run" which gave the output as the flag. Then the flag was copied and pasted into the flag box. 

```bash
touch /tmp/pwn
touch /tmp/college
/challenge/run
Success! Here is your flag:
pwn.college{EE0ddeE5-zJgkpaU6reTmW-BA7Q.QXwMDO0wCM4EzNzEzW}
```

### New Learnings
-> A new, blank file can be created by the touch command.

### References 
The module instruction was used.



## Challenge 8: removing files
This challenge tells the usage and implementation of rm command.

### Solve
**Flag:** `pwn.college{EzP4psqKLjSdw7T8tN3K1rOOeg2.QX2kDM1wCM4EzNzEzW}`

This challenge uses rm command to remove files. First, we were supposed to create a file name "delete_me" and then use the rm command to delete it by typing "rm delete_me" in the terminal. Then run "/challenge/check" in the terminal to get the output as the flag. Then the flag was copied and pasted into the flag box.

```bash
touch delete_me
rm delete_me
/challenge/check
Excellent removal. Here is your reward:
pwn.college{EzP4psqKLjSdw7T8tN3K1rOOeg2.QX2kDM1wCM4EzNzEzW}
```

### New Learnings
-> In Linux, you remove files with the rm command

### References 
The module instruction was used.



## Challenge 9: moving files
This challenge tells the usage and implementation of mv command.

### Solve
**Flag:** `pwn.college{AwOnnjbSPW1v8AJUsbRpRFUKOGc.0VOxEzNxwCM4EzNzEzW}`

This challenge asks us to use the mv command to move files. First, we are supposed to create a "hack-the-planet" file using the "touch /tmp/hack-the-planet" command. Then, we use "mv /flag /tmp/hack-the-planet" to move the file from flag to hack-the-planet. Run "/challenge/check" to get output as flag. Then the flag was copied and pasted into the flag box.

```bash
touch /tmp/hack-the-planet
mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
/challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{AwOnnjbSPW1v8AJUsbRpRFUKOGc.0VOxEzNxwCM4EzNzEzW}
```

### New Learnings
-> Moving files can be done with the mv command.

### References 
The module instruction was used.



## Challenge 10: hidden files
This challenge tells us how to access the hidden files.

### Solve
**Flag:** `pwn.college{gew_7LPej9B4a23sdtljKnXlmHU.QXwUDO0wCM4EzNzEzW}`

This challenge makes us use the "-a" to access hidden file. First, find the list of all directories/files in "/" using "ls -a /". There was one file name ".flag-233523129179". To find the flag, we need to read the file using "cat /.flag-233523129179" which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
ls -a /
.           .flag-233523129179  challenge  home   lib64   mnt  proc  sbin  tmp
..          bin                 dev        lib    libx32  nix  root  srv   usr
.dockerenv  boot                etc        lib32  media   opt  run   sys   var
cat /.flag-233523129179
pwn.college{gew_7LPej9B4a23sdtljKnXlmHU.QXwUDO0wCM4EzNzEzW}
```

### New Learnings
->  Linux has a convention where files that start with a . don't show up by default in ls and in a few other contexts.
-> To view them with ls, you need to invoke ls with the -a flag.

### References 
The module instruction was used.



## Challenge 11: An epic filesystem quest
This challenge is a game that is played using commands such as cd, ls and cat.

### Solve
**Flag:** `pwn.college{0ZxWLDMukKb0sNZGzYIPDxRtNAg.QX5IDO0wCM4EzNzEzW}`

This challenge is a long game where you have to satisfy conditions given by the terminal and solve to get the flag. A series of clues and restrictions were given which had to be solved to finally get the flag.

### New Learnings
-> uses of cd, ls, ls-a and cat commands

### References 
The module instruction was used.



## Challenge 12: making directories
This challenge tells the usage and implementation of mkdir command.

### Solve
**Flag:** `pwn.college{s1IdDBzdclhN6l6cBLhZ_3zOtgv.QXxMDO0wCM4EzNzEzW}`

This challenge uses the mkdir command to make a new directory. First make the directory "/tmp/pwn" using "mkdir /tmp/pwn". Then use "cd /tmp/pwn" to enter the common directory. Then make a college file using touch command as "touch college". Run "/challenge/run" to get output as flag. Then the flag was copied and pasted into the flag box.

```bash
mkdir /tmp/pwn
cd /tmp/pwn
touch college
/challenge/run
Success! Here is your flag:
pwn.college{s1IdDBzdclhN6l6cBLhZ_3zOtgv.QXxMDO0wCM4EzNzEzW}
```

### New Learnings
-> You make directories using the mkdir command. 

### References 
The module instruction was used.



## Challenge 13: finding files
This challenge tells the usage and implementation of find command.

### Solve
**Flag:** `pwn.college{k0Rl4vj-rooIK1Y0DxaVnWYHOCy.QXyMDO0wCM4EzNzEzW}`

This challenge uses the find command to search for a file. To find the file with the name flag "find / -name flag" is executed. A number of files with and without permission were displayed. Since, the file is not in the files which denied permission, using the cat command the contents of the file were read. Giving the input as "cat /usr/local/lib/python3.8/dist-packages/async_lru/__pycache__/flag" gave the output as the flag. Then the flag was copied and pasted into the flag box.


```bash
find / -name flag
cat /usr/local/lib/python3.8/dist-packages/async_lru/__pycache__/flag
pwn.college{k0Rl4vj-rooIK1Y0DxaVnWYHOCy.QXyMDO0wCM4EzNzEzW} 
```

### New Learnings
-> The find command takes optional arguments describing the search criteria and the search location. 
-> If you don't specify a search criteria, find matches every file. If you don't specify a search location, find uses the current working directory.

### References 
The module instruction was used.



## Challenge 14: linking files 
This challenge tells the usage and implementation of links.

### Solve
**Flag:** `pwn.college{I14KsOi7bqn9GY899a7NiPfxBYI.QX5ETN1wCM4EzNzEzW}`

This challenge makes use of symbolic links to solve the problem. First, I removed the not-the-flag file and any symbolic links to it. Then, a symbolic link was created between flag and not-the-flag. By doing this, not-the-flag can access the contents of the flag file. The flag file can then be run through /challenge/catflag which reads the not-the-flag file which gives the output as the flag. Then the flag was copied and pasted into the flag box.

```bash
rm /home/hacker/not-the-flag
ln -s /flag /home/hacker/not-the-flag
ls -l /home/hacker/not-the-flag
lrwxrwxrwx 1 hacker hacker 5 Sep 24 11:40 /home/hacker/not-the-flag -> /flag
/challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{I14KsOi7bqn9GY899a7NiPfxBYI.QX5ETN1wCM4EzNzEzW}
```

### New Learnings
-> when you want two programs to access the same data, but the programs expect that data to be in two different locations, then you use links
-> Two types: hard link and soft link. 

### References 
The module instruction was used.