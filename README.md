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
![306664559-5e7536db-fd1a-4b3f-9358-211a771e8100](https://github.com/23014282/2a_Stop_and_Wait_Protocol/assets/150009571/2fc2074f-d221-4cc7-8406-9bb90bc1a4b8)


SERVER
![306664797-08351b08-bc67-42a0-975a-88d1f145a355](https://github.com/23014282/2a_Stop_and_Wait_Protocol/assets/150009571/26c3bf86-61b9-4cf9-9730-b42c3fa9b422)


RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
