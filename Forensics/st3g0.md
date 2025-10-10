## st3g0
Download this image and find the flag.
Given image: https://artifacts.picoctf.net/c/217/pico.flag.png

### Solve
**Flag:** `picoCTF{7h3r3_15_n0_5p00n_a9a181eb}$t3g0`

Since this is a steganography solution, stego analysis tool "zsteg" was used. The command "zsteg pico.flag.png" was given in the bash which contained the flag in its input as "b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a9a181eb}$t3g0"". Since, it was given that the flag ends with $t3g0, "picoCTF{7h3r3_15_n0_5p00n_a9a181eb}" is our flag.

### New Learnings
-> use of zsteg for solving steganography problems 

### References 
-> https://www.garykessler.net/library/steganography.html
-> https://hexmos.com/freedevtools/tldr/common/zsteg/