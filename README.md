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
client
~~~
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
~~~
server
~~~
2.server
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
~~~
## OUTPUT
clint 
<img width="847" height="176" alt="image" src="https://github.com/user-attachments/assets/6b62474a-77d0-46ce-9d29-3ecd9a4b8579" />
server
<img width="847" height="141" alt="image" src="https://github.com/user-attachments/assets/3ed904a6-8998-4349-ba53-9f50777c8ca9" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
