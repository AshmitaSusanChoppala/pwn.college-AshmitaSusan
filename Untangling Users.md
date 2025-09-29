# Untangling Users

-> The full list of users on a Linux system is specified in the /etc/passwd file (named so for historical reasons --- it doesn't actually hold passwords anymore).
-> One important user is root: the system administrator. The system administrator has obvious security implications: a hacker user that can somehow, through various functionalities of Linux, become the root user would be able to wreak havoc on the system. A very frequent goal of hackers breaking into systems is to escalate to root, and thus root must be defended at all cost

## Challenge 1: Becoming root with su
This challenge covers the way of becoming root with su (the substitute user command).

### Solve
**Flag:** `pwn.college{YnH1S8mPf0J07dAmudkfQPp4_L_.QX1UDN1wCM4EzNzEzW}`

To become the root, first su command was run. The password was typed (given as hack-the-planet) and then pressed enter. It is now in the root directory. Then the flag was read using "cat /flag". Then the flag was copied and pasted into the flag box.

```bash
su
Password: 
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{YnH1S8mPf0J07dAmudkfQPp4_L_.QX1UDN1wCM4EzNzEzW}
```

### New Learnings
-> Becoming root is a fairly common action that Linux users take, and there are two utilities that exist for this purpose: su and sudo
-> su is a setuid binary because it has the SUID bit set, su runs as root.
-> Running as root, it can start a root shell
-> su is discerning: before allowing the user to elevate privileges to root, it checks to make sure that the user knows the root password

### References 
The module instruction was used.



## Challenge 2: Other users with su
The implementation of su with other users other than the root 

### Solve
**Flag:** `pwn.college{II0HspLO89QtwvWdKJTs4hYGeE_.QX2UDN1wCM4EzNzEzW}`

First, to switch to zardus user, "su zardus" was run in the terminal. The password was entered, which was given to be "dont-hack-me". Now, that we have entered the zardus user "/challenge/run" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{II0HspLO89QtwvWdKJTs4hYGeE_.QX2UDN1wCM4EzNzEzW}
```

### New Learnings
-> you can also give a username as an argument to switch to that user instead of root.

### References 
The module instruction was used.



## Challenge 3: Cracking passwords
Cracking leaked passwords using john

### Solve
**Flag:** `pwn.college{MLidtClVLkCkfwfg4Huc9rG7QDO.QX3UDN1wCM4EzNzEzW}`

First, to crack the zardus' leaked password, we can use "john" as so "john /challenge/shadow-leak", which leaked the password to be "aardvark". Then, to switch to zardus user, "su zardus" was run in the terminal. The password was entered. Now, that we have entered the zardus user "/challenge/run" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
john /challenge/shadow-leak
Created directory: /home/hacker/.john
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04826g/s 281.0p/s 281.0c/s 281.0C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{MLidtClVLkCkfwfg4Huc9rG7QDO.QX3UDN1wCM4EzNzEzW}
```

### New Learnings
-> When you enter a password for su, it compares it against the stored password for that user. These passwords used to be stored in /etc/passwd, but because /etc/passwd is a globally-readable file, this is not good for passwords, these were moved to /etc/shadow.
-> Separated by :s, the first field of each line is the username and the second is the password. A value of * or ! functionally means that password login for the account is disabled, a blank field means that there is no password, and passwords can also be stored by one-way-encrypting(hashing).
-> cracking passwords can be done via john.

### References 
The module instruction was used.



## Challenge 4: Using sudo
This challenge deals with the implementation of sudo

### Solve
**Flag:** `pwn.college{QRM8u737XlQumbV0gI8IlH-ufWB.QX4UDN1wCM4EzNzEzW}`

To read the flag by becoming the root (by using sudo), "sudo cat /flag" was given as the input, which gave the flag as the output. Then the flag was copied and pasted into the flag box.

```bash
sudo cat /flag
pwn.college{QRM8u737XlQumbV0gI8IlH-ufWB.QX4UDN1wCM4EzNzEzW}
```

### New Learnings
-> a typical Linux system had a root password that administrators would use to su to root (after logging into their account with their normal account password). But root passwords are a pain to maintain, they (or their hashes!) can leak, and they don't lend themselves well to larger environments (e.g., fleets of servers).
-> sudo originally stood for superuser do, but has changed to "su 'do'", and because su stands for "substitute user", the current meaning of sudo is "substitute user, do"
-> sudo defaults to running a command as root
->  sudo checks policies to determine whether the user is authorized to run commands as root. These policies are defined in /etc/sudoers.

### References 
The module instruction was used.