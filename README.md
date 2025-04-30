# HTTP-SERVER-IN-JAVA

This project implements a basic HTTP/1.1 server in Java that can handle multiple clients concurrently. The server is part of the "Build Your Own HTTP server" challenge from CodeCrafters.

## Features
1. Multi-threaded Server
   
   - Listens on port 4221
   - Handles multiple client connections concurrently using threads
   - Supports keep-alive connections
2. HTTP Methods Support
   
   - GET: For retrieving resources
   - POST: For uploading files
3. Endpoints
   
   - / - Returns 200 OK with empty response
   - /echo/<message> - Returns the message in the response
   - /user-agent - Returns the client's User-Agent header
   - /files/<filename> - Handles file operations:
     - GET: Retrieves file content
     - POST: Uploads file content
4. Advanced Features
   
   - Content type detection based on file extensions
   - GZIP compression support
   - Keep-alive connection handling
   - Proper HTTP header parsing
   - Error handling (404 Not Found, 405 Method Not Allowed)
## Technical Implementation
### Main Components
1. Server Initialization ( `main` )
   
   - Creates a ServerSocket on port 4221
   - Accepts client connections in an infinite loop
   - Spawns new thread for each client connection
2. Client Handler ( `handleClient` )
   
   - Processes HTTP requests
   - Parses headers and request line
   - Routes requests to appropriate handlers
   - Manages connection lifecycle
3. Response Handler ( `sendResponse` )
   
   - Constructs HTTP responses
   - Handles content type detection
   - Implements GZIP compression
   - Manages response headers
