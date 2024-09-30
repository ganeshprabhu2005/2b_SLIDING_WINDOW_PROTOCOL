# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

```
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
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
 
## OUPUT
![365882306-813b2b66-c154-47ae-ba05-a558b811eaf5](https://github.com/user-attachments/assets/a035b206-fdfb-4584-ad7a-d2c0f23c89e7)



![365882397-d51d24a4-9ead-4fe9-bd5b-180d4e245f56](https://github.com/user-attachments/assets/c71d2c37-b027-40fe-afa8-3db62ab63af5)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
