# Chapter 1 Computer Networks and the Internet

## 1.1 What is the Internet?

* We can describe the nuts and bolts of the Internet, that is, the basic hardware and software components that make up the Internet.
* We can describe the Internet in terms of a networking infrastructure that provides services to distributed applications.

### A Nuts-and-Bolts Description

The Internet is a computer network that interconnects hundreds of millions of computing devices throughout the word.

**Host :** A computer connected to the Internet or another IP-based network.

**End System :** The computers that are connected to a computer network. 

**Packets :** The resulting packages of information sent through the network to the destination end system.

### A Services Description

The Internet is an infrastructure that provides services to applications.

End systems attached to the Internet provide an **Application Programming Interface \(API\)** that specifies how a program running on one end system asks the Internet infrastructure to deliver data to a specific destination program running on another end system.

### Protocol

A Protocol defines the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.

## 1.2 The Network Core

**Packet Switching :** Most packet switches use store-and-forward transmission at he inputs to the links. It means that the packet switch must receive the entire packet before it can begin to transmit the first bit of the packet onto the outbound link.

**Circuit Switching :** In circuit-switched networks, the resources needed along a path \(buffers, link transmission rate\) to provide for communication between the end systems are reserved for the duration of the communication session between the end system.

Packet switching is not suitable for real-time services, but there are two advantages: \(1\)--it offers better sharing of transmission capacity than circuit switching; \(2\) it is simpler, more efficient, and less costly to implement than circuit switching.

## 1.3 Delay, Loss, and Throughput in Packet-Switched Networks

A packet  travels from one node to the subsequent node along a path suffers from several types of delays at each node along the path. The most important of these delays are the **nodal processing delay**, **queuing delay**, **transmission delay**, and **propagation delay**.

#### Processing Delay

* Time required to check bit errors, and determine output link.
* Order of microseconds or less.

#### Queuing Delay

* Time required to wait to be transmitted onto the link.
* Order of microseconds to milliseconds.

#### Transmission Delay

* Time required to push all of the packet's bits into the link.
* Order of microseconds to milliseconds.
* Denote the length of the packet by _L_ bits, and denote the transmission rate between two routers is _R_ bits/sec, the transmission delay is L/R.

#### Propagation Delay

* Time required to propagate from the beginning of the link to another router.
* Order of milliseconds.
* The propagation delay is d/s, where d is the distance between two routers and s is the propagation speed of the link.

#### Packet Loss

In reality a queue preceding a link has finite capacity. Therefore, with on place to store such a packet, a router will drop that packet; that is, the packet will be lost.



