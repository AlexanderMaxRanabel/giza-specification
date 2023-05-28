Giza Protocol Specification
Version: 1.1

1. Protocol Overview:
The Giza protocol enables communication between clients and a display server. It facilitates the rendering and composition of graphical elements on the display, as well as handling user input events.

2. Protocol Components:
The Giza protocol consists of the following components:

2.1. Client:
- The client is an application or entity that interacts with the display server.
- The client sends requests to the display server for rendering and input handling.

2.2. Compositor:
- The compositor is the central component of the display server responsible for managing the composition of graphical elements.
- It receives requests from clients and coordinates the rendering process and distributes episodes / divided requests beetween sub-compositors.

2.3. Sub-compositor:
- Sub-compositors are specialized components within the compositor that handle specific episodes or tasks.
- They receive episodes from the main compositor and perform translation and processing.

2.4. Kernel:
- The Kernel mostly represents Linux kernel.
- The kernel represents the underlying operating system and hardware.
- Sub-compositors communicate with the kernel to interact with the display hardware and manage input events.

3. Protocol Operations:
The Giza protocol supports the following operations:

3.1. Rendering Operations:
- Client requests the creation, update, or removal of graphical elements.
- The compositor receives these requests and performs the necessary composition and rendering.

3.2. Input Handling:
- Client sends input events, such as mouse or keyboard events, to the display server.
- The display server processes and dispatches these events to the appropriate client or application.

4. Protocol Message Format:
The Giza protocol uses a binary message format for communication. Each message consists of a header and a payload.

4.1. Message Header:
The message header includes the following fields:
- Magic Number: A unique identifier indicating the protocol. Must be 14 character long.
- Message Length: The length of the entire message (header + payload).
- Message Type: Specifies the type of message (e.g., request, response, event).
- Message ID: An identifier for tracking requests and matching responses.

4.2. Payload:
The payload contains the specific data for each message type. The format of the payload varies depending on the operation being performed.

5. Security Considerations:
- Giza protocol should incorporate secure communication mechanisms, such as encryption and authentication, to protect against unauthorized access or tampering.
- Implement proper access control and privilege management to ensure that only authorized clients can interact with the display server.
- Handle input events securely to prevent potential security vulnerabilities or exploits.

6. Versioning and Compatibility:
- The Giza protocol should support versioning to accommodate future enhancements and changes.
- Version negotiation mechanisms should be in place to ensure compatibility between different protocol versions.
