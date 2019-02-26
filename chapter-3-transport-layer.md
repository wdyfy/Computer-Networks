# Chapter 3 Transport Layer

## 3.1 Introduction and Transport-Layer Services

There are two distinct transport-layer protocols available to the application layer:

**UDP**\(User Datagram Protocol\): provides an unreliable, connectionless service to the invoking application.

**TCP**\(Transmission Control Protocol\): provides a reliable, connection-oriented service to the invoking application.

The most fundamental responsibility of UDP and TCP is to extend IP's delivery service between two end systems to a delivery service between two process running on the end systems. Extending host-to-host delivery to process-to-process delivery is called transport-layer multiplexing and demultiplexing.

## 3.2 Multiplexing and Demultiplexing

Demultiplexing: At the receiving end, the transport layer examines fields \(each transport layer segment has a set of fields\) to identify the receiving socket and then directs the segment to the socket. Each socket in the host could be assigned a port number, and when a segment arrives at the host, the transport layer examines the destination port number in the segment and directs the segment to the corresponding socket. The segment's data then passes through the socket into the attached process.

Multiplexing: gathering data chunks at the source host from different sockets, encapsulating each data chunk with header information to create segments, and passing the segments to the network layer. In a host, transport-layer multiplexing requires: \(1\) sockets have unique identifiers and \(2\) each segment have **source port number field** and the **destination port number field** that indicate the socket to which the segment is to delivered.













