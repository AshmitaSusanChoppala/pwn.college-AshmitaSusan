# Cryptography

## Challenge

### Solve

nc filtermaze.2025.ctfcompetition.com 1337
== proof-of-work: enabled ==
please solve a pow first
You can run the solver with:
    python3 <(curl -sSL https://goo.gle/kctf-pow) solve s.AJyu.AAD5X0BZUjlNwuvK/4N+2vML
===================

Solution? s.AAAZ9VOj8JnU972LCDXbs15n2XZGZ9G+KXeySfL8D3LqpZUo8YnA3R1ddw3e5GGx0mxFSfXGeUdX/LFK5ToVMrPJpfALndkwh2JBBMT78Hr6W/e7qJZnGzWAN3EnwyPqkY5m8w7kGVbikqV9lejASr7VkGLTXWR/WIh66f0XPE6/PTkaPCCph5KU9pg0YfjIjKMXFcDxYtYrp+m4GTSvz0Pk

[python kctf_pow.py solve s.AJyu.AAD5X0BZUjlNwuvK/4N+2vML
Solution:
s.AAAZ9VOj8JnU972LCDXbs15n2XZGZ9G+KXeySfL8D3LqpZUo8YnA3R1ddw3e5GGx0mxFSfXGeUdX/LFK5ToVMrPJpfALndkwh2JBBMT78Hr6W/e7qJZnGzWAN3EnwyPqkY5m8w7kGVbikqV9lejASr7VkGLTXWR/WIh66f0XPE6/PTkaPCCph5KU9pg0YfjIjKMXFcDxYtYrp+m4GTSvz0Pk]

Correct
Welcome! I've hidden the key at the end of the maze. You can use this to open the chest to get the flag.
Commands: {"command": "check_path", "segment": [...]}
          {"command": "get_flag", "lwe_secret_s": [...] }

According to filtermaze.py, our path is a hamiltonian path starting from 0 and using graph.json we can find out the hamiltonian path(goes through each vertex only once) using trial and error.

{"command": "check_path", "segment": [0,15,1,16,2,17,3,18,4,19,5,20,6,21,7,22,8,23,9,24,10,25,11,26,12,27,13,28,14,29]}
{"status": "path_complete", "lwe_error_magnitudes": [265, 622, 38, 716, 722, 308, 996, 799, 742, 337, 927, 698, 626, 969, 330, 126, 321, 20, 271, 839, 175, 399, 752, 989, 666, 629, 271, 400, 311, 840, 821, 821, 17, 978, 488, 781, 74, 818, 849, 903, 776, 142, 505, 951, 582, 638, 222, 872, 427, 165, 307, 209, 475, 970, 748, 814, 69, 213, 27, 742, 744, 566, 262, 852, 740, 309, 997, 502, 995, 434, 405, 193, 257, 953, 924, 678, 232, 226, 560, 414, 584, 579, 767, 810, 51, 894, 446, 281, 761, 908, 715, 787, 722, 270, 94, 169, 474, 431, 292, 346]}

The next command is {"command": "get_flag", "lwe_secret_s": [...] }

I've tried using the s array/vector in the "lwe_secret_params" file which I got when I ran the "filtermaze.py". But that showed the output as invalid key.
I've also tried using python script to calculate the s values using the public parameters but to no avail.

