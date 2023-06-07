# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

## DATE : 06-03-2023

### AIM :
To write a python program to perform stop and wait protocol

### ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program

### PROGRAM :
```
Developed by: Harini.B
Register Number: 212221230035
```
### CLIENT PROGRAM :
```
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
   i=input("Enter a data:")
   c.send(i.encode())
   ack=c.recv(1024).decode()
   if ack:
   	print(ack)
   	continue
   else:
   	c.close()
   	break
```

### SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())
```

### OUTPUT:
![outc](https://github.com/HariniBaskar/19CS406-EX-1/assets/93427253/22f570b2-3345-48db-8c7e-2d6b716ca0fb)

### RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
