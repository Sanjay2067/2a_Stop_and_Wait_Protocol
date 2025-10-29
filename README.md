# 2a_Stop_and_Wait_Protocol
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
```
1.Client
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
2.Server
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
1 Client
<img width="1037" height="210" alt="Screenshot 2025-09-02 212804" src="https://github.com/user-attachments/assets/0c42240c-b04b-49cd-a508-a6eb3748cafd" />

2.Server
<img width="1039" height="132" alt="Screenshot 2025-09-02 212831" src="https://github.com/user-attachments/assets/42f004bc-5f2c-40c8-b1fd-4da494348a01" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
