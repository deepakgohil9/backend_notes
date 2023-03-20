## 💫 TCP/IP & OSI Model 

During the development of network protocol we came up with 2 models :

*   TCP/IP
*   OSI

Then we adopted the TCP/IP model and nowadays TCP/IP is used as a network protocol.

---

## 💫 OSI Model

When you take the network, it a gigantic topic to discuss. The OSI Model helps us better understand it.This model is categorized into 7 layers. So through each layer, we will be able to understand how data is traveling from one system to another through the internet.

### Layer 7 : Application Layer

This layer interacts with the application, communicating with the network. There are several protocols which are used in this layer and they are HTTP, Telnet, POP3 or SMTP (for email purposes), FTP, IMAP, etc. So the particular application allows this layer to send data and receive data from the Presentation layer.

### Layer 6 : Presentation Layer

This layer is responsible for converting data according to the end system’s syntax or semantics. This layer is also called the **Syntax Layer** because this layer manages the encryption and decryption. Finally, before transferring data to the Session layer, the presentation layer compresses the data received from the application layer. By reducing the quantity of data exchanged, it helps to enhance communication speed and efficiency.

### Layer 5 : Session Layer

The session layer will establish communication channels between devices, which will be referred to as sessions. This layer is in charge of starting such sessions and making sure they work during data transfer. This layer is responsible for establishing, managing, terminating, and communicating sessions. This layer manages different types of connections as well as authentication and re-connection in the event of a network interruption.

### Layer 4 : Transport Layer

This layer is mainly responsible for data transmission across the network connection**, error checking, flow control,** and **sequencing data packets.** This layer determines how much data to send, how fast it should be sent, and where it should be sent, among other factors. **TCP** and **UDP** are the protocols used in this layer.

### Layer 3 : Network Layer

The IP header which is attached to the data in this layer. In the header, you can see there are a source address and destination address which will have the IP addresses of the sender and the receiver respectively. So, this packet will be sent to a specific destination based on the destination address.

### Layer 2 : Data Link Layer

This layer is considered the most complex layer of all 7 and this layer corrects the errors(if any occurred in the physical layer). This will ensure error-free data transmission between nodes through the physical layer. Here the data is called frames. There are two subsections in this layer, such as **MAC (Media Access Control)** and **LLC (Logical Link Control).**

*   **MAC (Media Access Control) —** Flow control and multiplexing device communications over the network are handled by the MAC address layer.
*   **LLC (Logical Link Control) —** Over the physical media, the LLC layer offers error control and flow control, as well as identifying network layer protocols from the header.

### Layer 1 : Physical Layer

This is the lowest layer of the OSI model where network devices take part entirely, such as cables, routers, switches, and hubs, etc. This layer is responsible for the actual physical connection between network devices and over the physical layer of the world. Here the data is transferred in the form of bits**.** So**,** when receiving data, this layer receives the signal and converts it to 0s and 1s before sending it to the Data Link layer.

---

## 💫 TCP/IP Model

In the OSI Model there are only 5 layers:

1.  Physical Layer
2.  Data Link Layer
3.  Network Layer
4.  Transport Layer
5.  Application Layer

All the above 4 layers are the same as the 4 layers of the OSI Model, and the rest of the 3 layers of the OSI model are merged into one called the **Application Layer** in the TCP/IP model.
