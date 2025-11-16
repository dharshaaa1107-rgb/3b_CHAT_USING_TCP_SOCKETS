# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
SERVER
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

print("Server started… Waiting for client...")
c, addr = s.accept()
print("Connected with:", addr)

while True:
    ClientMessage = c.recv(1024).decode()
    print("Client >", ClientMessage)

    msg = input("Server > ")
    c.send(msg.encode())
```
CLIENT
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")
    s.send(msg.encode())

    print("Server >", s.recv(1024).decode())
```

## OUPUT
<img width="1185" height="621" alt="image" src="https://github.com/user-attachments/assets/6f7ab45e-e5f2-4a4e-a1cf-716ce5070d56" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
