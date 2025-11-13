# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM

Server :
```
# echo_server.py
import socket

# Step 1: Create a socket object
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Step 2: Bind to localhost and port
server_socket.bind(('127.0.0.1', 65432))

# Step 3: Listen for connections
server_socket.listen(1)
print("Server is listening on port 65432...")

# Step 4: Accept connection
conn, addr = server_socket.accept()
print(f"Connected by {addr}")

while True:
    data = conn.recv(1024)
    if not data:
        break
    print("Received from client:", data.decode())
    conn.sendall(data)  # Echo the data back

# Step 5: Close connection
conn.close()
server_socket.close()

````
Client :

```
# echo_client.py
import socket

# Step 1: Create a socket object
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Step 2: Connect to the server
client_socket.connect(('127.0.0.1', 65432))

# Step 3: Send data
message = input("Enter a message to send: ")
client_socket.sendall(message.encode())

# Step 4: Receive response
data = client_socket.recv(1024)
print("Echoed from server:", data.decode())

# Step 5: Close connection
client_socket.close()
```
    
## OUPUT

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8058b34b-d0b0-4e4c-915d-af0a0187cc97" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
