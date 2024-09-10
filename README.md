# Socket
### Overview
The mChat system is a simple client-server chat application. The server handles multiple clients, who can join chat channels, send messages, and interact in real time. The system supports features like muting, kicking users, and managing multiple channels.

### Prerequisites
Python 3.x
Libraries: socket, threading, queue, sys, time, and os.
### Files
mchatserver.py: Implements the server-side logic of the chat system.
mchatclient.py: Implements the client-side logic for interacting with the server.
## mchatserver.py (Server)
### How to Run:
Ensure Python 3.x is installed.
Run the server:
`python mchatserver.py <config_file>`
Replace `<config_file>` with the path to the configuration file that contains channel details.
### Features:
Multiple Clients: Handles multiple clients connecting and interacting in a chat channel.
Channel Management: Channels can be created, each with a specific port and capacity.
Client Management: Clients can be muted, kicked, or placed in a waiting queue if the channel is full.
Configuration: A configuration file is used to define the channels (name, port, capacity).
### Configuration File:
The configuration file should contain lines in the following format:
`<channel_name> <port> <capacity>`
## mchatclient.py (Client)
### How to Run:
Run the client after starting the server:
`python mchatclient.py <username> <port>`
Replace `<username>` with the desired username and `<port>` with the channel's port number.
### Features:
Connect to Server: Connects to the server using TCP over a specified port.
Send/Receive Messages: Sends chat messages to the server and receives broadcasts from other users.
Disconnect: Gracefully disconnects from the chat.
### Example Usage
Start the server:
`python mchatserver.py config.txt`
Connect multiple clients:
`python mchatclient.py Alice 8080`
`python mchatclient.py Bob 8080`
