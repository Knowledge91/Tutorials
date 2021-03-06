In the *Open Systems Interconnection* (OSI) model *Transmission Control Protocol* (TCP) forms part of the transport layer (4th Layer). We have to use sockets to send datagrams between client and the server. C++ has a socket library `<sys/socket.h>`.
# TCP Server
- create socket with `socket(...)`
- reserve the socket address (port) `bind(...)`
- listen for clients `listen(...)`
- create a new socket to receive datagrams from a client `accept(...)`
- read received datagram `read(...)`
- respond to client `write(...)`

# TCP Client
- create socket with `socket(...)`
- connect to server with `connect(...)`
- send datagram to connected server with `send(...)`
- receive response from server with `read(...)`

# HTTP Server
To complete the HTTP server we have to have to give the TCP datagram a valid HTTP response:
`std::string hello = "HTTP/1.1 200 OK\nContent-Type: text/plain\nContent-Length: 12\n\nHello world!";`

## Lessons
- convert `string` to `char *` use
```
  std::string str;
  char * c = str.c_str();
```
