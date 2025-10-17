## Disk, disk, sleuth! II
All we know is the file with the flag is named `down-at-the-bottom.txt`... Disk image: dds2-alpine.flag.img.gz
using sleuthkit to solve the challenge

### Solve
**Flag:** `picoCTF{f0r3ns1c4t0r_n0v1c3_f5565e7b}`

The given file "dds2-alpine.flag.img.gz" was first unzipped and extracted which gave us a disk file named "dds2-alpine.flag". To analyse the file, it was opened in autopsy. It was given that the name of the file with the flag is `down-at-the-bottom.txt`. The file was then searched which could be done manually or using keyword search. Manually, the file was found in "Data Sources -> dds2.alpine.flag.img.gz -> dds2-alpine.flag.img -> vol2 -> root -> down-at-the-bottom.txt". The file was opened and the flag was found.

### New Learnings
-> Learning the use and application of sleuthkit and autopsy

### References 
https://www.youtube.com/watch?v=fEqx0MeCCHg
https://www.sleuthkit.org/