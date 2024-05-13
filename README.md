2a_Stop_and_Wait_Protocol
Name: A.JEEVITH
Reg.NO: 212223240059
AIM
To write a python program to perform stop and wait protocol

ALGORITHM
Start the program.
Get the frame size from the user
To create the frame based on the user request.
To send frames to server from the client side.
If your frames reach the server it will send ACK signal to client
Stop the Program
PROGRAM
CLIENT
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
SERVER
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
OUTPUT
CLIENT
image

SERVER
image

RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
