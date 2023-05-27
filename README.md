## EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL
```
DATE: 16-03-2023
```
### AIM :
To write a python program to perform stop and wait protocol.

### ALGORITHM :
```
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program
```

### PROGRAM :
```
Developed By: G Venkata Pavan Kumar
Reg. No.: 212221240013
```
#### Client:
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
#### Server:
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
~~~
### OUTPUT :
#### Client Side:
![image](https://github.com/Pavan-Gv/EX-2/assets/94827772/110f94e7-88ba-4975-8a1f-bea44b922ea2)
#### Server Side:
![image](https://github.com/Pavan-Gv/EX-2/assets/94827772/550ea1fe-fbc6-4b22-a4d6-4ad13e97d529)
### RESULT :
Thus, python program to perform stop and wait protocol was successfully executed.
