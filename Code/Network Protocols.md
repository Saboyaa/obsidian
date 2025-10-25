`Protocols` are standardized rules that determine the formatting and processing of data to facilitate communication between devices in a [[network]]. These protocols operate at different layers within network models, each tailored to handle specific types of data and communication needs. Here’s a look at some common network protocols and their roles in data exchange.

## Common Network Protocols

- `HTTP (Hypertext Transfer Protocol)` Primarily used for transferring web pages. It operates at the Application Layer, allowing browsers and servers to communicate in the delivery of web content.

- `FTP (File Transfer Protocol)` Facilitates the transfer of files between systems, also functioning at the Application Layer. It provides a way for users to upload or download files to and from servers.

- `SMTP (Simple Mail Transfer Protocol)` Handles the transmission of email. Operating at the Application Layer, it is responsible for sending messages from one server to another, ensuring they reach their intended recipients.

- `TCP (Transmission Control Protocol)` Ensures reliable data transmission through error checking and recovery, operating at the Transport Layer. It establishes a connection between sender and receiver to guarantee the delivery of data in the correct order.

- `UDP (User Datagram Protocol)` Allows for fast, connectionless communication, which operates without error recovery. This makes it ideal for applications that require speed over reliability, such as streaming services. UDP operates at the Transport Layer.

- `IP (Internet Protocol)` Crucial for routing packets across network boundaries, functioning at the Internet Layer. It handles the addressing and routing of packets to ensure they travel from the source to the destination across diverse networks.
### Dynamic Host Configuration Protocol (DHCP)
`DHCP` is a network management protocol used to automate the process of configuring devices on IP networks. It allows devices to automatically receive an IP address and other network configuration parameters, such as subnet mask, default gateway, and DNS servers, without manual intervention.

It works in 2 roles:
- `DHCP Server` A network device (like a router or dedicated server) that manages IP address allocation. It maintains a pool of available IP addresses and configuration parameters.
- `DHCP Client` Any device that connects to the network and requests network configuration parameters from the DHCP server.
And the communication is by the DORA process
1.  `Discover` When a device connects to the network, it broadcasts a **DHCP Discover** message to find available DHCP servers.
 2. `Offer` DHCP servers on the network receive the discover message and respond with a **DHCP Offer** message, proposing an IP address lease to the client.
3. `Request` The client receives the offer and replies with a **DHCP Request** message, indicating that it accepts the offered IP address.
4. `Acknowledge` The DHCP server sends a **DHCP Acknowledge** message, confirming that the client has been assigned the IP address. The client can now use the IP address to communicate on the network.
### Network Address Translation (NAT)
`Network Address Translation (NAT)` is a process carried out by a router or a similar device that modifies the source or destination IP address in the headers of IP packets as they pass through. This modification is used to translate the private IP addresses of devices within a local network to a single public IP address that is assigned to the router.
#### Types of NAT
 - `Static NAT` Involves a one-to-one mapping, where each private IP address corresponds directly to a public IP address.
 - `Dynamic NAT` Assigns a public IP from a pool of available addresses to a private IP as needed, based on network demand.
- `Port Address Translation (PAT)` Also known as NAT Overload, is the most common form of NAT in home networks. Multiple private IP addresses share a single public IP address, differentiating connections by using unique port numbers. This method is widely used in home and small office networks, allowing multiple devices to share a single public IP address for internet access.
