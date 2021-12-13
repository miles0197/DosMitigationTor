# DoS attack attempt on a test relay
## Tor's Hammer code is not written by me, I do not advise to use it carelessly.

-> Create a virtual machine, setup your network configurations (Host-only or Shared)

-> Under the OS of your choice, configure Tor Project’s repository and install Tor. I used Debian Ububntu.
   https://support.torproject.org/apt/
   
   
-> Modify /etc/tor/torrc file in your intention (Nickname, Control port, Relay test, Sockslisten, ORport, HashedControlPassword authentication etc.)


-> Control Tor client from control port #it is set 9051 or 9050 by default I belive (study the torrc file carefully)


-> Enable the system for tor (systemctl enable tor) and start tor (systemctl start tor)


-> Dowlonad Nyx, a command-line application for monitoring real time Tor status info.
   $apt-get install nyx
   
   
   
-> Start netcat and test the connection between client and local host (listen port allows certain incoming connections to bind etc.) The control port is opened on      localhost.
   Reference link: https://github.com/iavael/torcat

-> You could test and monitor tcp connections, 3 way handshakes(SYN, SYN-ACK, ACK) that are established using Wireshark.



-> Attack using the Tor's hammer python script based on slow post tool. Before doing so, study how the script is constructed and learn to use it. As localhost, make    sure IP/Server/Port are set with necessary permissions. (see  /etc/tor/torrc)



-> Attack your own relay and look for event messages, bandwidth limit, follow your findings.



#Disclaimer: This article is just for knowledge purpose. Please don’t use this article to perform any malicious activity. Remember, before targeting or attacking anyone’s IP/hostname/Servers one must have the necessary permissions.**
