# 4.Execution_of_NetworkCommands
## NAME : Nithish R
## Reg No :212223040135
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

### PROGRAM
### PING COMMAND
### CLIENT
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
### SERVER
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### TRANCEROUTE COMMAND
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
### PING COMMAND
### CLIENT
![image](https://github.com/Magathi7/4.Execution_of_NetworkCommends/assets/144870480/4327fa44-3b3c-4df7-a299-2f825d045a91)
### SERVER
![image](https://github.com/Magathi7/4.Execution_of_NetworkCommends/assets/144870480/5490cabe-9b1e-430b-b2b4-c5502e2ff0ef)
### TRANCEROUTE COMMAND
![image](https://github.com/Magathi7/4.Execution_of_NetworkCommends/assets/144870480/f757da8a-228d-4da9-9581-f22eb076c9a0)
## Result
Thus Execution of Network commands Performed 
