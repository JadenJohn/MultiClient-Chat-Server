# CHAT SERVER (CLIENT-SERVER)

C++ Boost.Asio Multi-threaded Chat Server and Client

This project implements a console-based chat application using C++11 and the Boost.Asio asynchronous networking library. It features both a chat server and multiple chat clients, communicating over TCP sockets.

FEATURES

Asynchronous Server & Client:
Built with Boost.Asio’s async model for non-blocking communication.

Thread Pool with Strand:
The server uses a thread pool with boost::asio::io_service::strand (or boost::asio::strand in newer versions) to ensure serialized handler execution. This removes the need for manual synchronization like mutexes or locks in the server’s thread pool.

Broadcast Messaging:
Each message sent by a client is broadcast to all clients connected to the same chat room.

Message Format:

->Messages include:
->Server timestamp
->Sender's nickname
->Message content

Chat History:
When a new client joins, the server sends them the recent chat history from the room they joined.

Multi-room Support:
A single server can host multiple chat rooms, each identified by a different port number.

Thread Configuration:
The number of worker threads is currently hardcoded for demo purposes. In production, it should be loaded from a configuration file.

CPU Affinity on Linux:
Demonstrates how to bind threads to specific CPU cores for performance tuning.

Cross-Platform:
Tested on both Windows and Linux environments.
