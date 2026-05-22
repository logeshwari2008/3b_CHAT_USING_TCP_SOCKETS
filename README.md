# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
chat server
```
import socket 
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
host = '127.0.0.1' 
port = 5000 
server_socket.bind((host, port)) 
server_socket.listen(1) 
print("Waiting for client connection...") 
client_socket, addr = server_socket.accept() 
print("Connected to:", addr) 
while True:
    client_message = client_socket.recv(1024).decode() 
    print("Client:", client_message) 
    if client_message.lower() == "bye":
        break 
    message = input("Server: ") 
    client_socket.send(message.encode()) 
    if message.lower() == "bye":
        break 
client_socket.close() 
server_socket.close()
```
chat client
```
import socket 
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
host = '127.0.0.1' 
port = 5000 
client_socket.connect((host, port)) 
print("Connected to server") 
while True:
    message = input("Client: ") 
    client_socket.send(message.encode()) 
    if message.lower() == "bye":
        break 
    server_message = client_socket.recv(1024).decode() 
    print("Server:", server_message) 
    if server_message.lower() == "bye":
        break 
client_socket.close()
```
## OUPUT
chat server
<img width="1469" height="375" alt="image" src="https://github.com/user-attachments/assets/1b089875-e288-4670-b4bb-2b7825e8ef0b" />
chat client
<img width="1372" height="337" alt="image" src="https://github.com/user-attachments/assets/49e2986c-b662-4d20-b359-93792d5a4681" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
