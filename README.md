# 4.Execution_of_NetworkCommands
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

## Program
server.py

```
import socket
import subprocess

# Create socket
s = socket.socket()

# Bind host and port
s.bind(("localhost", 5000))

# Listen for client
s.listen(1)

print("Server waiting for connection...")

# Accept connection
c, addr = s.accept()

print("Connected with:", addr)

# Receive website/IP from client
host = c.recv(1024).decode()

# Execute ping command
result = subprocess.getoutput("ping " + host)

# Send result to client
c.send(result.encode())

# Close connections
c.close()
s.close()
```

client.py

```
import socket

# Create socket
c = socket.socket()

# Connect to server
c.connect(("localhost", 5000))

# Get website/IP from user
host = input("Enter website/IP: ")

# Send to server
c.send(host.encode())

# Receive and print result
print(c.recv(4096).decode())

# Close connection
c.close()
```

traceroute.py

```
import subprocess

target = input("Enter website or IP: ")

subprocess.run(["tracert", target])
```

## Output
server.py

<img width="428" height="167" alt="image" src="https://github.com/user-attachments/assets/698c18e1-775e-4ac7-92fa-6f5f7455c2cf" />


client.py


<img width="707" height="345" alt="image" src="https://github.com/user-attachments/assets/8fc0f0b7-5239-413e-ba8e-dcf27cf7e0ae" />



Traceroute.py


<img width="840" height="392" alt="image" src="https://github.com/user-attachments/assets/7aaab599-1318-44ca-9f3f-bc4f73791705" />




## Result
Thus Execution of Network commands Performed 
