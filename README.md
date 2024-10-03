An API for directly capturing packets from the datalink layer of Unix-derived operating systems is provided by the open-source C library libpcap. It allows widely used packet capture programs, such tcpdump and snort, to function on almost any Unix flavor.

This is an illustration of a basic libpcap-based packet sniffer program that shows packet data in a style similar like Snort.
Prerequisite : Libpcap
Run these command to install libpcap :sudo apt-get install libpcap-dev

Compilation:
g++ sniffer.cpp -o sniffer -lpcap

Tests

ICMP Capture
Run the command ping 8.8.8.8 on one terminal 
then run the sniffer to capture 4 ICMP packets on another terminal sudo ./sniffer -n 4 icmp.


<img width="498" alt="Screenshot 2024-10-03 165458" src="https://github.com/user-attachments/assets/c31ce5c4-4f97-46b8-b741-436c6ff38423">

UDP Capture 
Run the command 
nc -u www.google.com 53 < /dev/random on first terminal

Run the sniffer application to get UDP packets on port 53 on another terminal
sudo ./sniffer udp port 53 -n 5

<img width="464" alt="image" src="https://github.com/user-attachments/assets/2b38cf82-6842-48b7-828d-fdaeb2363b75">
