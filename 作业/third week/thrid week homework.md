#### Chapter 2 Problem 6

+ question:

    Obtain the HTTP/1.1 specification (RFC 2616). Answer the following questions:

    a. Explain the mechanism used for signaling between the client and server to indicate that a persistent connection is being closed. Can the client, the server, or both signal the close of a connection?
    
    b. What encryption services are provided by HTTP?
    
    c. Can a client open three or more simultaneous connections with a given server?
    
    d. Either a server or a client may close a transport connection between them if either one detects the connection has been idle for some time. Is it possible that one side starts closing a connection while the other side is transmitting data via this connection? Explain

+ Answer:
    + a) Persistent connections are discussed in section 8 of RFC 2616 (the real purpose of this question is to let you retrieve and read an RFC). Sections 8.1.2 and 8.1.2.1 of the RFC state that either a client or a server can indicate to the other that it will close a persistent connection. It does this by including the connection token "close" in the connection header field of the HTTP request/reply. 
    + b) HTTP does not provide any encryption services. 
    + c) Clients using persistent connections should limit the number of simultaneous connections they maintain to a given server. A single user client should not maintain more than two connections to any server or agent. 
    + d) yes.  The client may start sending new requests at the same time as the server decides to close the "idle" connection. From the server's point of view, the connection is closed when idle, but from the client's point of view, the request is in progress.