# layer 4

The most common protocols in the ⟮transport⟯ layer are ⟮TCP⟯ and ⟮UDP⟯. 
The ⟮transport⟯ layer, directly beneath the ⟮application⟯, but above the ⟮internet⟯ layer is the ⟮2nd⟯ layer from the top of the internet portocol suite. 
⟮TCP⟯ is ⟮more complex⟯ than ⟮UDP⟯ (amongst other things) because it is ⟮stateful⟯ 

## nc

nc as a command is read netcat
nc allows you to make raw TCP/UDP connections.
nc [‹options›] [‹hostname›] [‹port›]

## ports

Ports exist only in software 
A ⟮port⟯ is ⟮uniquely identified by⟯ a ⟮port number⟯. 
A ⟮port number⟯ is a ⟮16⟯ bit integer 
Ports that are ⟮only used for a short time⟯ to do something are known as ⟮ephemeral⟯ ports, which are generally used for ⟮clients⟯ (because ⟮the port of the client can be anything anyway⟯) 
the ⟮dynamic⟯ or ⟮private⟯ ports are often used as ⟮ephemeral⟯ ports 

Port range|Is called
⟮c+;‹1024⟯|⟮well-known⟯
⟮1024 - 49151 (2^15 + 2^14⟯)|⟮registered⟯
⟮49152 (2^15 + 2^14) - 2^16⟯|⟮dynamic⟯|⟮private⟯



Generally, an ⟮application protocol⟯ will have a ⟮port number⟯ it ⟮is associated with⟯ (esp. on ⟮the server side⟯). 

### preassigned

Protocol|Port
FTP|21
⟮SSH⟯|⟮22⟯
⟮telnet⟯|⟮23⟯
⟮SMTP (plaintext⟯)|⟮25⟯
⟮DNS⟯|⟮53⟯
⟮HTTP⟯|⟮80⟯
⟮IMAP (plaintext⟯)|⟮143⟯
⟮HTTPS⟯|⟮443⟯
⟮SMTP (encrypted⟯)|⟮587⟯
⟮IMAP (encrypted⟯)|⟮993⟯


### conventional

HTTP dev servers|8080 or 8000

ports below 1024 require root permission to open

## sockets

TCP|stream sockets
UDP|datagram sockets
A socket is a software interface to handle incoming/outgoing network traffic.
The most common type of socket is network/internet socket, and thus is often just called socket.
A network/internet socket exists at the transport layer
The socket address of a network/internet socket is the combination of IP address and port number.
A network/internet socket is minimally identified by the combination of socket address and transport protocol
A network/internet socket that has been connected to another socket (e.g. when using TCP), also is identified by the remote socket address.

## TCP

TCP = Transmission Control Protocol
TCP but not UDP can deal with / solve packets arriving out of order, lost packets (retransmits them), error detection, flow ＆ congestion control

### starting operations

TCP: Passive open → Active open
Passive open: The server binds to and listens at a port.
Active open: The client starts the 3-way/3-step handshake at the port.

#### TCP three-step handshake

Client --SYN-→ Server
Client ←-SYN-ACK-- Server
Client --ACK--→ Server

### normal operation

TCP requires the reciever to respond with an acknowledgement message for each message
in TCP, the client must retransmit the packet if a certain amount of time passes without recieving this acknowledgement message

### segment header

the TCP segment header contains 9 1-bit flags amongst which are the ones used for connection management (handshake, termination, etc.)
TCP uses a sequence number in the header to determine the order of the bytes to allow the data to be reconstructed if out of order.
The TCP sequence number should be unpredictable, or it is vulnerable to TCP sequence prediction attacks, where the attacker substitutes the packets.

## UDP


### Datagram header

the UDP ⟮datagram header⟯ consists of ⟮4⟯ ⟮fields⟯ of ⟮2⟯ ⟮bytes⟯ for a total of ⟮8⟯ ⟮bytes⟯ (⟮64⟯ ⟮bit⟯)


field|optionality
source port|optional
destination port|mandatory
length|mandatory
checksum|mandatory in IPv6


octets|0 ＆ 1|2 ＆ 3
!type=th;0|style=background-color: #fa9;Source port|Destination port
!type=th;4|Length|style=background-color: #fa9;Checksum

### Datagram

the maximum size of a ⟮UDP datagram⟯ is ⟮2^16 bytes⟯ (although IPv6 ⟮jumbograms⟯ do allow more, and ⟮headers⟯ take up some of that)

## TCP vs UDP

UDP can be significantly faster than TCP because TCP may wait seconds for out-of-order messages or retransmissions of lost messages, etc.