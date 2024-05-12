# 2a_Stop_and_Wait_Protocol

### NAME: POOJA A
### Register No: 212222240072
### Date: 12-05-2024

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
### Client:
```python
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

### Server:
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT
### Client:
![328116852-db6a49c3-88ae-4aa6-a3f8-55358939d957](https://github.com/poojaanbu0/2a_Stop_and_Wait_Protocol/assets/119390329/65319d61-b7c5-4fd3-b74a-dd8f1e72cc19)

### Server:
![328116975-3d52126d-d346-40b6-b273-8f59c55c80a4](https://github.com/poojaanbu0/2a_Stop_and_Wait_Protocol/assets/119390329/703b657a-ec69-4f50-a4a5-e4732bfe64aa)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
