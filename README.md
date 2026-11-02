# Ex.No: 1a – Study of Socket Programming

**Name:** MANORAJAPRIYAN.L.E  
**Reg. No:** 212225040227  

## AIM

To perform a study on Socket Programming and understand its fundamental concepts, operations, and applications in network communication.

## INTRODUCTION

Socket programming is a crucial aspect of network communication that allows data exchange between computers over a network. It forms the backbone of various networked applications, enabling communication between clients and servers.

This study explores the fundamental concepts of socket programming, its use cases, and provides practical examples to demonstrate its implementation.

## UNDERSTANDING SOCKET PROGRAMMING

Socket programming involves the use of sockets, which serve as endpoints for communication. A socket is identified by an IP address and a port number and facilitates data transfer between a client and a server.

The two main types of sockets are:

- **Stream Sockets:** Provide reliable, connection-oriented communication using TCP.
- **Datagram Sockets:** Provide connectionless communication using UDP and are suitable for applications where reliability is less critical.

## KEY CONCEPTS IN SOCKET PROGRAMMING

### 1. Sockets

- A socket is a software representation of a communication endpoint in a network.
- It is identified by an IP address and a port number.
- Sockets are classified into Stream Sockets and Datagram Sockets.
- Stream Sockets provide reliable communication, while Datagram Sockets operate in a best-effort mode.

### 2. Client-Server Model

- Socket programming typically follows the client-server model.
- The server listens for incoming connections from clients.
- The client initiates a connection to the server.
- Servers are passive, waiting for connection requests, while clients are active.

### 3. TCP/IP Protocol

- Transmission Control Protocol (TCP) and Internet Protocol (IP) are the foundational protocols for socket programming.
- TCP provides reliable, connection-oriented communication, ensuring data integrity and order.
- IP facilitates the routing of data between devices in a network.

### 4. Basic Socket Functions

Socket programming involves a set of functions used to create, bind, listen, accept, connect, send, and receive data.

Common socket functions include:

- `socket()` – Creates a socket.
- `bind()` – Assigns an IP address and port to a socket.
- `listen()` – Waits for incoming connection requests.
- `accept()` – Accepts an incoming connection.
- `connect()` – Establishes a connection with a server.
- `send()` – Sends data through a socket.
- `recv()` – Receives data through a socket.

## SERVER-SIDE OPERATIONS

- The server creates a socket using `socket()`.
- It binds the socket to a specific IP address and port using `bind()`.
- It listens for incoming connections using `listen()`.
- It accepts connections using `accept()`.
- After establishing a connection, the server sends and receives data using `send()` and `recv()`.

## CLIENT-SIDE OPERATIONS

- The client creates a socket using `socket()`.
- It connects to the server using `connect()`.
- After establishing a connection, the client sends and receives data using `send()` and `recv()`.
- Finally, the client closes the connection using `close()`.

## USE CASES OF SOCKET PROGRAMMING

Socket programming finds applications in various domains, including:

- Web development
- File transfer protocols
- Online gaming
- Real-time communication
- Remote procedure calls (RPC)

It is the foundation for protocols such as HTTP, FTP, and SMTP, which facilitate communication over the internet.

## EXAMPLE USE CASES

1. **Web Servers:** Handle incoming HTTP requests and serve web pages.
2. **Chat Applications:** Enable real-time communication between users.
3. **File Transfer Protocol:** Transfer files between clients and servers.
4. **Networked Games:** Facilitate communication between game clients and servers.
5. **RPC Mechanisms:** Allow processes to execute code on remote servers through network communication.

## SERVER PROGRAM

```python
import socket

# Create socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind socket to IP and port
host = '127.0.0.1'
port = 12345
server_socket.bind((host, port))

# Listen for connections
server_socket.listen(1)
print("Server is waiting for connection...")

# Accept client connection
conn, addr = server_socket.accept()
print("Connected to:", addr)

# Receive data from client
data = conn.recv(1024).decode()
print("Client says:", data)

# Send response to client
message = "Hello Client, message received!"
conn.send(message.encode())

# Close connection
conn.close()
server_socket.close()
```

## CLIENT PROGRAM

```python
# Client Program (client.py)
import socket

# Create socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect to server
host = '127.0.0.1'
port = 12345
client_socket.connect((host, port))

# Send message to server
message = "Hello Server!"
client_socket.send(message.encode())

# Receive response from server
data = client_socket.recv(1024).decode()
print("Server says:", data)

# Close socket
client_socket.close()
```

## OUTPUT

<img width="1920" height="1080" alt="Screenshot (72)" src="https://github.com/user-attachments/assets/ff55df9d-22fc-4a37-b874-c33ef8163706" />


## RESULT

Thus, the study of Socket Programming was completed successfully, and the basic communication between a client and a server was understood and demonstrated using Python.
