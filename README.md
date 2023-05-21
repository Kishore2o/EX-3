# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## DATE : 23-03-2023
## AIM :
To write a python program to perform sliding window protocol
## ALGORITHM :
```
 1.Start the program.
 2.Get the frame size from the user
 3.To create the frame based on the user request.
 4.To send frames to server from the client side.
 5.If your frames reach the server it will send ACK signal to client otherwise it will send NACKsignal to client.
    Stop the program
 ```
## PROGRAM :
## CLIENT :
```
# Developed By : KISHORE.S
# Register Number : 22008388
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
    while(i<len(l)):
        st+=s
        c.send(str(l[i:st]).encode())
        ack=c.recv(1024).decode()
        if ack:
            print(ack)
            i+=s
          
 ```
## SERVER :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```
## OUTPUT :
## CLIENT :
![c op](https://github.com/Kishore2o/EX-3/assets/118679883/f5a3dba5-6ec2-4b16-b90c-db9eca23b407)


## SERVER :
![s op](https://github.com/Kishore2o/EX-3/assets/118679883/570e244f-2a97-4362-91d6-951c06ba10c2)


## RESULT :
Thus, python program to perform stop and wait protocol And Sliding Window Protocol was successfully executed.
