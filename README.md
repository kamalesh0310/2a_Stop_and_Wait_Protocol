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
Server.py:
~~~
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
Client.py:
~~~
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
~~~
## OUTPUT
server
<img width="1153" height="250" alt="Screenshot 2026-02-05 162856" src="https://github.com/user-attachments/assets/3ba1fb5b-2be6-4229-b33d-0e5985e379cd" />

client
<img width="882" height="177" alt="Screenshot 2026-02-05 162926" src="https://github.com/user-attachments/assets/d92b0187-d649-4fc2-a75d-ba294d598e19" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
