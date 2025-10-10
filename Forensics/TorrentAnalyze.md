## Torrent Analyze
SOS, someone is torrenting on our network.
One of your colleagues has been using torrent to download some files on the company’s network. Can you identify the file(s) that were downloaded? The file name will be the flag, like picoCTF{filename}
Given file: https://artifacts.picoctf.net/c/165/torrent.pcap

### Solve
**Flag:** `picoCTF{ubuntu-19.10-desktop-amd64.iso}`

Given file is a file with pcap extenstion. For analyzing packets, wireshark can be used. So, the file was opened using wireshark. Hint 2: You may want to enable BitTorrent protocol (BT-DHT, etc.) on Wireshark. Analyze -> Enabled Protocols. Following hint 2, BT_DHT protocol was enabled. While searching through the BT-DHT files,we find the ones having info hash in it's info column. bt-dht.bencoded.string contains info_hash was given in the filter box.Following this we can manually search each hash in google to find reference to hash e2467cbf021192c241367b892230dc1e05c0580e on linuxtracker.org which was given as "ubuntu-19.10-desktop-amd64.iso" and they said the file ends in iso, so "ubuntu-19.10-desktop-amd64" is our file name.


### New Learnings
-> analyzing a file using wireshark.
-> The info hash is a SHA-1 hash of the bencoded info dictionary within the torrent file. 

### References 
-> https://www.youtube.com/watch?v=a_4MjV_-7Sw&t=206s
-> https://www.techworm.net/2017/03/seeds-peers-leechers-torrents-language.html