# Chapter 3 Transport Layer

## 3.1 Introduction and Transport-Layer Services

There are two distinct transport-layer protocols available to the application layer:

**UDP**\(User Datagram Protocol\): provides an unreliable, connectionless service to the invoking application.

**TCP**\(Transmission Control Protocol\): provides a reliable, connection-oriented service to the invoking application.

The most fundamental responsibility of UDP and TCP is to extend IP's delivery service between two end systems to a delivery service between two process running on the end systems. Extending host-to-host delivery to process-to-process delivery is called transport-layer multiplexing and demultiplexing.

## 3.2 Multiplexing and Demultiplexing

Demultiplexing: At the receiving end, the transport layer examines fields \(each transport layer segment has a set of fields\) to identify the receiving socket and then directs the segment to the socket. Each socket in the host could be assigned a port number, and when a segment arrives at the host, the transport layer examines the destination port number in the segment and directs the segment to the corresponding socket. The segment's data then passes through the socket into the attached process.

Multiplexing: gathering data chunks at the source host from different sockets, encapsulating each data chunk with header information to create segments, and passing the segments to the network layer. In a host, transport-layer multiplexing requires: \(1\) sockets have unique identifiers and \(2\) each segment have **source port number field** and the **destination port number field** that indicate the socket to which the segment is to delivered.

### Connectionless Multiplexing and Demultiplexing

Example: With port numbers assigned to UDP sockets, we can now precisely describe UDP multiplexing/demultiplexing. Suppose a process in Host A, with UDP port 19157, wants to send a chunk of application data to a process with UDP port 46428 in Host B. The transport layer in Host A creates a transport-layer segment that includes the application data, the source port number \(19157\), the destination port number \(46428\), and two other values \(which will be discussed later, but are unim- portant for the current discussion\). The transport layer then passes the resulting seg- ment to the network layer. The network layer encapsulates the segment in an IP datagram and makes a best-effort attempt to deliver the segment to the receiving host. If the segment arrives at the receiving Host B, the transport layer at the receiving host examines the destination port number in the segment \(46428\) and delivers the segment to its socket identified by port 46428. Note that Host B could be running multiple processes, each with its own UDP socket and associated port number. As UDP segments arrive from the network, Host B directs \(demultiplexes\) each segment to the appropriate socket by examining the segment’s destination port number.

### Connection-Oriented Multiplexing and Demultiplexing

TCP socket is identified by a four-tuple: source IP address, source port number, destination IP address, destination port number. When a TCP segment arrives from the network to a host, the host uses all four values to direct the segment to the appropriate socket.







