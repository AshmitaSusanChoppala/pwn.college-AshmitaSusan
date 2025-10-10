## chall1
using encryption/decryprion techniques to find out the flag.

### Solve
**Flag:** `flaggg{w0w_g0od_j0b_V3ry_gr34t_amazing_AW35OMEE}`

By analysing the python file (chal.py), we understand that this is a cipher XOR script, with key given as "djpakoda" which repeats indefinitely, and the result is the ct file. Since, XOR is symmetric we can decrypt the ct file to get the flag again. Then, the cyberchef tool was used for decryption. XOR cipher was selected, key as "djpakoda" with "utf-8" or "latin1" setting (as can be seen through a hexedit tool, the first few bites are raw not hexadecimal), and input as the ct file which gave the output as the flag.

### New Learnings
-> implementation of XOR cipher

### References 
-> (https://gchq.github.io/CyberChef/)