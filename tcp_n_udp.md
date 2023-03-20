## 💫 TCP 

TCP (Transmission Control Protocol) is an important network protocol that lets two hosts connect and exchange data streams. TCP guarantees the delivery of data and packets in the same order as they were sent. TCP is one of the IP protocols.

TCP's role is to ensure the packets are reliably delivered and error-free. TCP implements congestion control, which means the initial requests start small, increasing in size to the levels of bandwidth the computers, servers, and network can support.

## 💫 UDP

UDP (User Datagram Protocol) is a long standing protocol used together with IP for sending data when transmission speed and efficiency matter more than security and reliability.

UDP uses a simple connectionless communication model with a minimum of protocol mechanism. UDP provides checksums for data integrity, and port numbers for addressing different functions at the source and destination of the datagram. It has no handshaking dialogues, and thus exposes the user's program to any unreliability of the underlying network.

## 💫 Difference

| TCP | UDP |
| --- | --- |
| secure | unsecure |
| connection-oriented | connectionless |
| slow | fast |
| guarantee transmission | no guarantee |
| used in critical applications | used in real-time applications |
| packet reorder mechanism | no reorder mechanism |
| flow control | no flow control |
| advance error checking | basic error checking (checksum) |
| acknowledgement mechanism | no acknowledgement mechanism |
| three-way handshake | no handshake mechanism |
| DNS, HTTPS, FTP, SMTP, etc | DNS, DHCP, TFTP, SNMP, etc |
