# File Globbing

## Challenge 1: Matching with *
This challenge specifies the use of *.

### Solve
**Flag:** `pwn.college{AIZzLNq0YNY4_vBGCMmUfwR1LpR.QXxIDO0wCM4EzNzEzW}`

The common working directory is by default in the /home/hacker directory. To change the directory to challenge using '*' and the argument being only four letters, the input was given as cd /ch *. Then "/challenge/run" was executed which gave the flag as the output. Then the flag was copied and pasted into the flag box. 

```bash
cd /ch*
/challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{AIZzLNq0YNY4_vBGCMmUfwR1LpR.QXxIDO0wCM4EzNzEzW}
```

### New Learnings
-> Before executing commands that you enter, the shell first performs expansions on them, and one of these expansions is globbing. Globbing lets you reference files without typing them all out, or typing out their full paths. 
-> When it encounters a * character in any argument, the shell will treat it as a "wildcard" and try to replace that argument with any files that match the pattern. 

### References 
The module instruction was used.



## Challenge 2: Matching with ?
This challenge specifies the use of ?.

### Solve
**Flag:** ``

The common working directory is by default in the /home/hacker directory. We have to change the directory to challenge using '?' and the argument cannot contain the letters c and l. Since, ? character matches only one character, the c and l in challenge are replaced by '?'. "cd /?ha??enge" is given to the input to change the directory. Then "/challenge/run" was executed which gave the flag as the output. Then the flag was copied and pasted into the flag box. 

```bash
cd /?ha??enge
/challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{UrM8UvyOlDoE_0EKf8SPO9wvw8Z.QXyIDO0wCM4EzNzEzW}
```

### New Learnings
-> When it encounters a ? character in any argument, the shell will treat it as a single-character wildcard. This works like *, but only matches one character.

### References 
The module instruction was used.



## Challenge 3: Matching with []
This challenge specifies the use of [].

### Solve
**Flag:** `pwn.college{k00Mn8_5hlL0pHoTq53tZgwfd8L.QXzIDO0wCM4EzNzEzW}`

First, we have to change the directory to "challenge/files" to access the files, this can done using "cd /challenge/files". The required files were file_b, file_a, file_s, and file_h. We can access them using bracket globs where we can put b,a,s,h into the bracket. The arguement to '/challenge/run' would be "file_[bash]". Then "/challenge/run file_[bash]" was executed which gave the flag as the output. Then the flag was copied and pasted into the flag box. 

```bash
cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{k00Mn8_5hlL0pHoTq53tZgwfd8L.QXzIDO0wCM4EzNzEzW}
```

### New Learnings
-> The square brackets are, essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets. 

### References 
The module instruction was used.



## Challenge 4: Matching paths with []
This challenge tells more about globbing using [].

### Solve
**Flag:** `pwn.college{A1GvjwRmKkOivgkTwIlMznU8Xuw.QX0IDO0wCM4EzNzEzW}`

Since, the absolute paths of each of the files are required, in the argument to "/challenge/run" the absolute path would be given as input along with the bracket glob of the required files. Therefore, the input would be "/challenge/run /challenge/files/file_[bash]" which would then give the output as the flag. Then the flag was copied and pasted into the flag box. 

```bash
/challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{A1GvjwRmKkOivgkTwIlMznU8Xuw.QX0IDO0wCM4EzNzEzW}
```

### New Learnings
-> Globbing happens on a path basis, so you can expand entire paths with your globbed arguments.

### References 
The module instruction was used.



## Challenge 5: Multiple globs
This challenge tells the use of having more than 1 glob in an argument.

### Solve
**Flag:** `pwn.college{AXhYAwDKUL3FHGmAT7ykNzW09JQ.0lM3kjNxwCM4EzNzEzW}`

First, we have to change the directory to "challenge/files", this can done using "cd /challenge/files". Then, the argument to "/challenge/run" should have 3 or less than 3 characters, should have two * globs and should cover every word that contains p. The most suitable argument would be *p*(anything can be before or after p). Then "/challenge/run *p*" was executed which gave the flag as the output. Then the flag was copied and pasted into the flag box. 

```bash
 cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{AXhYAwDKUL3FHGmAT7ykNzW09JQ.0lM3kjNxwCM4EzNzEzW}
```

### New Learnings
-> Bash supports the expansion of multiple globs in a single word.

### References 
The module instruction was used.



## Challenge 6: Mixing globs
This challenge makes use of all the globs used till now. 

### Solve
**Flag:** `pwn.college{sYFKsyHOBxu9nhaqWzihilrOFzG.QX1IDO0wCM4EzNzEzW}`

First, we have to change the directory to "challenge/files", this can done using "cd /challenge/files". We have to match the files "challenging", "educational", and "pwning" by using the globs discussed so far in 6 characters or less. We can use bracket globs to specify the first letter of each file and then we can use the * glob later(anything can after the first letters). Then "/challenge/run [cep]*" was executed which gave the flag as the output. Then the flag was copied and pasted into the flag box. 

```bash
cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{sYFKsyHOBxu9nhaqWzihilrOFzG.QX1IDO0wCM4EzNzEzW}
```

### New Learnings
-> Mixing or using different globs at the same time.

### References 
The module instruction was used.



## Challenge 7: Exclusionary globbing
This challenge tells the significance of ! in a bracket glob.

### Solve
**Flag:** `pwn.college{QisQUXk3DxnmZN3tw9VDoGDA-Ig.QX2IDO0wCM4EzNzEzW}`

First, we have to change the directory to "challenge/files", this can done using "cd /challenge/files". We have to match the files that do not start with p,w or n in 8 characters or less. We can use bracket globs to specify the ! symbol(for matching characters that weren't listed) and first letter of each file not needed and then we can use the * glob later(anything can after the first letters). Then "/challenge/run [!pwn]*" was executed which gave the flag as the output. Then the flag was copied and pasted into the flag box. 

```bash
cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{QisQUXk3DxnmZN3tw9VDoGDA-Ig.QX2IDO0wCM4EzNzEzW}
```

### New Learnings
-> [] helps you to filter out files in a glob
-> If the first character in the brackets is a ! or (in newer versions of bash) a ^, the glob inverts, and that bracket instance matches characters that aren't listed.
-> The ! character has a different special meaning in bash when it's not the first character of a [] glob., ^ does not have this problem, but is also not compatible with older shells.

### References 
The module instruction was used.



## Challenge 8: Tab completion
This challenge use tab to complete the path

### Solve
**Flag:** `pwn.college{89Vgn8wIuxeYvT35Bq_1Jo_Umo1.0FN0EzNxwCM4EzNzEzW}`

First, the command cat was specified, Then /challenge/pwn and then tab was pressed to complete the argument. "cat /challenge/pwn<TAB>" was executed which gave the flag as the output. Then the flag was copied and pasted into the flag box. 

```bash
cat /challenge/pwncollege​ 
pwn.college{89Vgn8wIuxeYvT35Bq_1Jo_Umo1.0FN0EzNxwCM4EzNzEzW}
```

### New Learnings
-> If you hit tab in the shell, it'll try to figure out what you're going to type and automatically complete it. Auto-completion is super useful, and this challenge will explore its use in specifying files.

### References 
The module instruction was used.



## Challenge 9: Multiple options for tab completion
This challenge addresses the situation where there are multiple options while using the tab command.

### Solve
**Flag:** `pwn.college{oOkjNkKuFyBwWGGBUnGVRxYcMg8.0lN0EzNxwCM4EzNzEzW}`

Used the tab options to navigate through each of the files and at then used cat to read the pwncollege-flag file which gave flag as the output. Then the flag was copied and pasted into the flag box. 

```bash
cat /challenge/files/pwn
pwn                    pwncollege-family      pwncollege-flyswatter
pwn-college            pwncollege-flag        pwncollege-hacking
pwn-the-planet         pwncollege-flamingo    
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-
pwncollege-family      pwncollege-flamingo    pwncollege-hacking
pwncollege-flag        pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-f
pwncollege-family      pwncollege-flamingo    
pwncollege-flag        pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-fl
pwncollege-flag        pwncollege-flamingo    pwncollege-flyswatter
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-fla
pwncollege-flag      pwncollege-flamingo  
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-flag
pwn.college{oOkjNkKuFyBwWGGBUnGVRxYcMg8.0lN0EzNxwCM4EzNzEzW}
```

### New Learnings
-> By default bash will auto-expand until the first point when there are multiple options (in this case, fl). When you hit tab a second time, it'll print out those options. Other shells and configurations, instead, will cycle through the options.

### References 
The module instruction was used.



## Challenge 10: Tab completion on commands
This challenge uses tab to complete the commands.

### Solve
**Flag:** `pwn.college{E3baYibHoQTdZJf57NmudqGMyWJ.0VN0EzNxwCM4EzNzEzW}`

First, pwncollege was entered as instructed and then tab key was used to autocomplete the rest of the command. "not-the-flag" file has the flag. "pwncollege-22481 not-the-flag" was executed which gave the flag as the output.Then the flag was copied and pasted into the flag box. 

```bash
pwncollege-22481 
.ICEauthority  .cache/        .dbus/         .local/        a
.bash_history  .config/       .lesshst       Desktop/       not-the-flag
hacker@globbing~tab-completion-on-commands:~$ pwncollege-22481 not-the-flag 
Correct! Here is your flag:
pwn.college{E3baYibHoQTdZJf57NmudqGMyWJ.0VN0EzNxwCM4EzNzEzW}
```

### New Learnings
-> You can also tab-complete commands.

### References 
The module instruction was used.