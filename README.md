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
server.py:
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)
c, addr = s.accept()

while True:
    msg = c.recv(1024).decode()
    if not msg: break
    print("Client:", msg)
    c.send(input("Server: ").encode())

c.close(); s.close()

```
Client.py:
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client: ")
    s.send(msg.encode())
    if msg == 'exit': break
    print("Server:", s.recv(1024).decode())

s.close()

```
## OUPUT
Server Output:

<img width="656" height="255" alt="image" src="https://github.com/user-attachments/assets/1b79dbe7-3f4c-4579-9833-41b12fd86589" />

Client Output:

<img width="665" height="261" alt="image" src="https://github.com/user-attachments/assets/4ce09a4d-2efb-40f3-a920-788b2e998376" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
