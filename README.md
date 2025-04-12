# 2a_Stop_and_Wait_Protocol
## Name: Madhupriya.R
## Reg no:212224040177
## AIM 
To write a python program to perform stop and wait protocol.
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## Client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
     print(ack)
     continue
    else:
      c.close()
      break
```
## Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT

<img width="479" alt="2025-04-12 (2)" src="https://github.com/user-attachments/assets/3061480b-f366-4f74-b2a0-1036f4c56931" />


<img width="475" alt="2025-04-12 (3)" src="https://github.com/user-attachments/assets/8cdfcc04-7e59-4a95-8746-bdb4d00bf37c" />




## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
