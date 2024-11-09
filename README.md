# 2a_Stop_and_Wait_Protocol
### Name:Vikaash K S
### Register Number: 212223240179
### Date: 27.08.2024

## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### CLient
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
### Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  print(s.recv(1024).decode())
  s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### Client
![exp 1a client](https://github.com/user-attachments/assets/5ecdf4fa-589d-4555-8963-b5ac4c713558)

### Server
![exp 1a server](https://github.com/user-attachments/assets/696cc172-6258-412c-92e2-d566a80d4073)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
