# IMPLEMENTATION OF STOP AND WAIT PROTOCOL 
## EXP:1(a)
## Date:
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

CLIENT:
```
import socket 
s=socket.socket() 
s.bind(('localhost',9000)) 
s.listen(5) 
c,addr=s.accept() 
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}; 
while True:
     ip=c.recv(1024).decode() 
     try: 
       c.send(address[ip].encode()) 
     except KeyError: 
       c.send("Not Found".encode()) 
```
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter MAC Address : ")
    s.send(ip.encode()) 
    print("Logical Address",s.recv(1024).decode()) 
```

## OUTPUT
CLIENT:

![Screenshot 2024-11-22 171523](https://github.com/user-attachments/assets/28e5af86-2c6e-4b62-9e8a-13052f44753d)

SERVER:

![Screenshot 2024-11-22 171543](https://github.com/user-attachments/assets/eca757c7-269b-4e90-a661-dcdad4fa29d2)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
