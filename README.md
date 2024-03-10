## SHREE LEKHA.S 212223110052
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
## PROGRAM:
### Client:
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()

while True:
    data = input("Enter data to send: ")
    c.send(data.encode())

    ack = c.recv(1024).decode()
    if ack == "Acknowledgement Received":
        print("Server acknowledged the data.")
    else:
        print("Error in acknowledgment. Closing connection.")
        c.close()
        break

c.close()
```

### Server:
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    received_data = s.recv(1024).decode()
    print("Received data:", received_data)

    ack_message = "Acknowledgement Received"
    s.send(ack_message.encode())
```
### PROBRAM:
![Screenshot 2024-03-10 190634](https://github.com/SHREELEKHAS/2a_Stop_and_Wait_Protocol/assets/149768910/b7c0f9a6-ae2a-4363-af52-3e3b5246bb61)









## OUTPUT:
![Screenshot 2024-03-10 190701](https://github.com/SHREELEKHAS/2a_Stop_and_Wait_Protocol/assets/149768910/3a769b48-5ebe-4501-acdb-ec824b4827e6)


## RESULT

Thus, python program to perform stop and wait protocol was successfully executed.
