# Forensics

## Gotham Hustle

### Solve
**Flag:** `bi0sctf{w3lc0m3_t0_df1r_l4iu_h0p3_th15_b3n3f175_y0u_m0r3_13337431}`

pypy vol.py -f /mnt/c/Users/csant/Downloads/gotham/gotham.raw --profile Win7SP1x64_23
418 cmdscan
Cmd #0 @ 0x12f7c0: whoami
Cmd #1 @ 0x130110: dir
Cmd #2 @ 0x12f800: bi0s
Cmd #3 @ 0x12f820: dfirlabs
Cmd #4 @ 0x12d690: Ymkwc2N0Znt3M2xjMG0zXw==
Cmd #5 @ 0x12d6d0: azr43ln1ght.github.io
Cmd #6 @ 0x125650: Azr43lKn1ght
Cmd #7 @ 0x125680: did you find flag1?
Cmd #15 @ 0xb0158:
Cmd #16 @ 0x12ff50:
**************************************************
CommandProcess: conhost.exe Pid: 4140
CommandHistory: 0x280e10 Application: DumpItog.exe Flags: Allocated
CommandCount: 0 LastAdded: -1 LastDisplayed: -1
FirstCommand: 0 CommandCountMax: 50
ProcessHandle: 0x10
Cmd #15 @ 0x200158: (
Cmd #16 @ 0x27ff70: (

base 64 decoding of "Ymkwc2N0Znt3M2xjMG0zXw==" : bi0sctf{w3lc0m3_

 pypy vol.py -f /mnt/c/Users/csant/Downloads/gotham/gotham.raw --profile=Win7SP1x64_23418 filescan | grep -F "bruc
e\\Desktop"
Volatility Foundation Volatility Framework 2.6.1
0x000000011ca4a800     15      0 R--rwd \Device\HarddiskVolume2\Users\bruce\Desktop\desktop.ini
0x000000011ec0eae0      2      1 R--rwd \Device\HarddiskVolume2\Users\bruce\Desktop
0x000000011ee1af20     13      0 R--r-d \Device\HarddiskVolume2\Users\bruce\Desktop\DumpItog.exe
0x000000011f2538c0      1      1 RW-rw- \Device\HarddiskVolume2\Users\bruce\Desktop\BRUCE-PC-20240806-183717.raw
0x000000011f558280      2      1 R--rwd \Device\HarddiskVolume2\Users\bruce\Desktop
0x000000011f97ca70      1      1 R--rw- \Device\HarddiskVolume2\Users\bruce\Desktop
0x000000011fdaff20     16      0 -W-r-- \Device\HarddiskVolume2\Users\bruce\Desktop\flag5.rarp\VirtualBox Dropped Files\2024-08-06T18_36_43.522668500Z\flag5.rar

Found a file with the name flag5.rar. Extracted it using:
pypy vol.py -f /mnt/c/Users/csant/Downloads/gotham/gotham.raw --profile=Win7SP1x64_23418 dumpfiles --dump-dir=output/ -Q 0x000000011fdaff20
Then downloaded it and ran for strings:
The password for the zip file is the computer's password..
I used the hashdump module to dump the NTLM hashes. The password gets cracked using crackstation.net. Using that password on the zip file gave me part 5 of the flag: m0r3_13337431}

There are a lot of chrome processes in the process list, The chromes history plugin was broken, So I used the working one from DFIR community repo:
https://raw.githubusercontent.com/superponible/volatility-plugins/master/sqlite_help.py

wget https://raw.githubusercontent.com/superponible/volatility-plugins/master/sqlite_help.py -O sqlite_help.py
--2025-12-10 12:01:33--  https://raw.githubusercontent.com/superponible/volatility-plugins/master/sqlite_help.py

ashmita@csanthisagar:~/volatility$ mv sqlite_help.py volatility/plugins/
ashmita@csanthisagar:~/volatility$ ls volatility/plugins/ | grep sqlite
sqlite_help.py
ashmita@csanthisagar:~/volatility$ pypy vol.py -f /mnt/c/Users/csant/Downloads/gotham/gotham.raw \
  --profile=Win7SP1x64_23418 chromehistory
Volatility Foundation Volatility Framework 2.6.1
Index  URL                                                                              Title                                                                            Visits Typed Last Visit Time            Hidden Favicon ID
------ -------------------------------------------------------------------------------- -------------------------------------------------------------------------------- ------ ----- -------------------------- ------ ----------
    20 https://www.google.com/search?q=flag3+%...l2.321545j0j7&sourceid=chrome&ie=UTF-8 flag3 = aDBwM190aDE1Xw== - Google Search                                              2 

flag3 = aDBwM190aDE1Xw which is then decoded to "h0p3_th15_"

pypy vol.py -f /mnt/c/Users/csant/Downloads/gotham/gotham.raw \ --profile=Win7SP1x64_23418 pslist
0xfffffa8003c9c4f0 notepad.exe            2592   1172      1       58      1      0 2024-08-06 16:47:20 UTC+0000
0xfffffa80039c2490 mspaint.exe            2516   1172      7      142      1      0 2024-08-06 18:35:09 UTC+0000
These look like known processes, so I tried dumping these processes and running strings on them.
ashmita@csanthisagar:~/volatility$ pypy vol.py -f /mnt/c/Users/csant/Downloads/gotham/gotham.raw \
  --profile=Win7SP1x64_23418 memdump --dump-dir=output -p 2592
Writing notepad.exe [  2592] to 2592.dmp
ashmita@csanthisagar:~/volatility$ strings output/2592.dmp | grep -i flag

flag4 = YjNuM2YxNzVfeTB1Xw== which decodes to "b3n3f175_y0u_" 

pypy vol.py -f /mnt/c/Users/csant/Downloads/gotham/gotham.raw \
  --profile=Win7SP1x64_23418 memdump --dump-dir=output -p 2516
 ls output/
2516.dmp  2592.dmp  _2516.dmp.extracted  file.None.0xfffffa80049f86a0.dat
ashmita@csanthisagar:~/volatility$ ls output/_2516.dmp.extracted/
13680353.gz  14E83F9F.obfuscated  161D2029       1634D9FF.gz  16616E81.gz  16A47800  16A5A000  16B77400  16B89800  16BAE300       1A154DAB.7z  50CB7CC     75EA452.7z
13681937.gz  15390D00             161D2029.zlib  163C0000.gz  166170A1.gz  16A49000  16A60000  16B7A800  16B8A300  16BAE400       1A16CDCB     50CB7CC.7z  F32DEE3
136823D3.gz  15391F00             161D3000       163C0F18.gz  166188F1.gz  16A4A000  16A61000  16B7A900  16B8A600  16BAE600       1A16CDCB.7z  53CA452     F32DEE3.7z
13B7DF87     15392800             161D5000       163C1D34.gz  166191D5.gz  16A4A800  16A62000  16B7C800  16B8A700  16BAE700       1C535060     53CA452.7z  FA4DD76.zip
13B7DF87.7z  15393400             161D5800       163C271C.gz  1661AE20.gz  16A4E800  16A63000  16B7D100  16B8A800  16BAE800       1C535060.7z  59EA452     ext-root
13EBB008     15AA5A76             161D6000       163C32F5.gz  1661BF53.gz  16A4F000  16A67000  16B7D500  16B9AE00  16BAF200       1C5B7053     59EA452.7z  ext-root-0
13EBB008.7z  15AA5A76.zlib        161D7000       163C8FC9.gz  166B1000     16A50000  16A68800  16B81800  16B9B500  16BAF400       1C5B7053.7z  649E3E6.7z  ext-root-1
140D6000     15AA5E76             161D7800       163C995A.gz  166B2181     16A51000  16A69000  16B81C00  16BA1F00  16BB2F00       1CEE6BF3     7297452
140DA000     15AA5E76.zlib        1633835A.gz    163CA972.gz  166C8ACB     16A51800  16A69800  16B83400  16BAD200  16F27F50.ext2  1CEE6BF3.7z  7297452.7z
140E1000     15F17E10.gz          16339845.gz    163CB0DF.gz  1685A275.gz  16A53000  16B76200  16B84000  16BAD300  1722AC20.ext2  1E45246.zip  741F174
145C7042     15FDE120.rar         1633AEBF.gz    163CCF7C.gz  168C7800     16A55000  16B76C00  16B88800  16BAD700  17B28130.ext2  504C084      741F174.7z
145C7042.7z  161AB000             16347471.gz    16616000.gz  16A47000     16A57000  16B77000  16B89500  16BADA00  1A154DAB       504C084.7z   75EA452

The last part of the flag was found using binwalk, foremost and other processes to get the flag2 as "dDBfZGYxcl9sNGl1Xw==" which decodes to "t0_df1r_l4iu_"

which combines to give the flag "bi0sctf{w3lc0m3_t0_df1r_l4iu_h0p3_th15_b3n3f175_y0u_m0r3_13337431}"


### New Learnings
-> using volatility
