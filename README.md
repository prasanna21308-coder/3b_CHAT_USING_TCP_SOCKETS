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
## SERVER.PY
```
import socket 
# Create socket 
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
# Bind host and port 
host = '127.0.0.1' 
port = 5000 
server_socket.bind((host, port)) 
# Listen for client 
server_socket.listen(1) 
print("Waiting for client connection...") 
# Accept connection 
client_socket, addr = server_socket.accept() 
print("Connected to:", addr) 
while True: 
# Receive message from client 
 client_message = client_socket.recv(1024).decode() 
 print("Client:", client_message) 
# Exit condition 
 if client_message.lower() == "bye": 
  break 
# Send message to client 
 message = input("Server: ") 
 client_socket.send(message.encode()) 
 if message.lower() == "bye": 
  break 
# Close connection 
client_socket.close() 
server_socket.close()
```
## CLIENT.PY
```
import socket 
# Create socket 
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
# Server details 
host = '127.0.0.1' 
port = 5000 
# Connect to server 
client_socket.connect((host, port)) 
print("Connected to server") 
while True: 
# Send message to server 
 message = input("Client: ") 
 client_socket.send(message.encode()) 
 if message.lower() == "bye": 
  break 
# Receive message from server 
 server_message = client_socket.recv(1024).decode() 
 print("Server:", server_message) 
 if server_message.lower() == "bye": 
  break 
# Close connection 
client_socket.close()
```
## OUTPUT

## SERVERSIDE

<img width="1682" height="211" alt="image" src="https://github.com/user-attachments/assets/7f673e6a-2266-4ae6-8e16-0e65090aa9a7" />

## CLIENTSIDE

<img width="1837" height="219" alt="image" src="https://github.com/user-attachments/assets/65d75a16-2d9a-432d-a296-440dd09fa5ad" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
