# TCP Three-Way Handshake Analysis

## Purpose

TCP uses a three-way handshake to establish a reliable connection between two devices before data transfer begins.

## Handshake Process

### SYN

The client sends a SYN packet to request a new TCP connection with the server.

### SYN-ACK

The server responds with a SYN-ACK packet, acknowledging the request and confirming it is ready for communication.

### ACK

The client sends an ACK packet confirming the response, completing the connection establishment process.

## Evidence

Wireshark captured:

- SYN packet
- SYN-ACK packet
- ACK packet

This demonstrated the TCP connection establishment process.

## Importance

The TCP handshake ensures both devices agree on communication parameters before exchanging application data, allowing TCP to provide reliable delivery.