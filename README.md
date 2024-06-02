# Advanced-chat-server-
Chat server with high level Archtecture capable to handle millions of users with caching and rubust database data transfer managment

### Discription
This Chat server leverages Tornado for its web server capabilities, providing non-blocking I/O for efficient handling of HTTP requests and WebSocket connections. Redis is used for managing the state of active WebSocket clients, ensuring efficient tracking and scalability. HDFS (Hadoop Distributed File System) is employed for scalable and reliable file storage, while HBase serves as the storage backend for persistent chat messages. Kafka is integrated for message queuing and broadcasting, enabling real-time communication across connected clients. Together, these frameworks create a robust and scalable server environment suitable for applications requiring real-time communication, file management, and persistent data storage.

# Server to client Communication Preview  


# SA 
This server is ideal for applications requiring real-time communication, scalable file management, and robust data storage and retrieval capabilities.
![Screenshot 2024-06-02 205404](https://github.com/brianlangay4/Advanced-chat-server-/assets/67788456/6c330d39-1334-4d44-8002-15644c15bbd5)

### Server Description

This server is a robust web application built using the Tornado framework, designed to handle file uploads and downloads, real-time chat functionality, and seamless integration with various data storage and message queuing systems. Here's a brief overview of its components and functionalities:

1. **Web Server (Tornado)**:
   - **FileUploadHandler**: Manages HTTP POST requests for file uploads. Files are stored in the Hadoop Distributed File System (HDFS).
   - **FileDownloadHandler**: Handles HTTP GET requests for downloading files from HDFS.
   - **ChatHandler**: Manages WebSocket connections for real-time chat. Each connected client is assigned a unique ID, and their state is tracked using Redis.

2. **Redis**:
   - **Client State Management**: Tracks the state of connected WebSocket clients, ensuring efficient management of active connections.

3. **HDFS (Hadoop Distributed File System)**:
   - **File Storage**: Provides scalable and reliable storage for uploaded files, accessible for both uploading and downloading operations.

4. **HBase**:
   - **Chat Messages Storage**: Stores chat messages for persistence, enabling retrieval and analysis of chat history.

5. **Kafka**:
   - **Message Queue**: Handles the broadcast of chat messages. A Kafka producer sends messages to a specific topic, and a Kafka consumer processes these messages to distribute them to all connected clients.

6. **Concurrency Management**:
   - Utilizes Tornado's non-blocking I/O capabilities and threading (for Kafka consumption) to handle multiple simultaneous operations efficiently.

### Key Features:
- **Real-Time Communication**: Supports real-time chat through WebSockets, ensuring instant message delivery and receipt.
- **Scalable File Management**: Allows users to upload and download files efficiently, with storage handled by HDFS.
- **Persistent Storage**: Uses HBase to store chat messages, enabling persistent chat history.
- **Efficient State Management**: Employs Redis to manage the state of WebSocket connections, ensuring scalability and reliability.
- **Message Broadcasting**: Uses Kafka for robust message queuing and broadcasting, ensuring messages are distributed to all clients efficiently.

