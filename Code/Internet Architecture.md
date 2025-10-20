`Internet Architecture` describes how data is organized, transmitted, and managed across [[networks]].
## Types of architecture 

| `Architecture`                                 | `Centralized`                   | `Scalability`        | `Ease of Management`               | `Typical Use Cases`                |
| ---------------------------------------------- | ------------------------------- | -------------------- | ---------------------------------- | ---------------------------------- |
| [[#Peer-to-Peer (P2P) Architecture\|P2P]]      | Decentralized (or partial)      | High (as peers grow) | Complex (no central control)       | File-sharing, blockchain           |
| [[#Client-Server Architecture\|Client-Server]] | Centralized                     | Moderate             | Easier (server-based)              | Websites, email services           |
| [[#Hybrid Architecture\|Hybrid]]               | Partially central               | Higher than C-S      | More complex management            | Messaging apps, video conferencing |
| [[#Cloud Architecture\|Cloud ]]                | Centralized in provider’s infra | High                 | Easier (outsourced)                | Cloud storage, SaaS, PaaS          |
| `SDN`                                          | Centralized control plane       | High (policy-driven) | Moderate (needs specialized tools) | Datacenters, large enterprises     |

### Peer-to-Peer (P2P) Architecture
In a `Peer-to-Peer (P2P`) network, each node, whether it's a computer or any other device, acts as both a client and a server.
This setup allows nodes to communicate directly with each other, sharing resources such as files, processing power, or bandwidth, without the need for a central server. 
P2P networks can be fully decentralized, with no central server involved, or partially centralized, where a central server may coordinate some tasks but does not host data.
#### Advantages
- `Scalability` Adding more nodes can increase total resources (storage, CPU, etc.).
- `Resilience` If one node goes offline, others can continue functioning.
- `Cost distribution` Resource burden, like bandwidth and storage, is distributed among peers, making it more cost-efficient.
#### Disadvantages
- `Management complexity` Harder to control and manage updates/security policies across all nodes
- `Potential reliability issues` If too many peers leave, resources could be unavailable.
- `Security challenges` Each node is exposed to potential vulnerabilities.

A popular example of Peer-to-Peer (P2P) architecture is torrenting, as seen with applications like BitTorrent. In this system, anyone who has the file, referred to as a `seeder`, can upload it, allowing others to download it from multiple sources simultaneously.

### Client-Server Architecture
The `Client-Server` model is one of the most widely used architectures on the Internet. In this setup, clients, which are user devices, send requests, such as a web browser asking for a webpage, and servers respond to these requests, like a web server hosting the webpage. 
This model typically involves centralized servers where data and applications reside, with multiple clients connecting to these servers to access services and resources.
![[Client_Server_Arch-1.webp]]
#### Advantage
- `Centralized control` Easier to manage and update.
- `Security` Central security policies can be applied.
- `Performance` Dedicated servers can be optimized for their tasks.
#### Disadvantage
- `Single point of failure` If the central server goes down, clients lose access.
- `High Cost and Maintenance` Setting up and sustaining a client-server architecture is expensive, requiring constant operation and expert management , making it costly to maintain.
- `Network Congestion` High traffic on the network can lead to congestion, slowing down or even disrupting connections when too many clients access the server simultaneously.

**Examples of this architecture:**
#### Single-Tier Architecture

In a `single-tier` architecture, the client, server, and database all reside on the same machine. This setup is straightforward but is rarely used for large-scale applications due to significant limitations in scalability and security.

#### Two-Tier Architecture

The `two-tier` architecture splits the application environment into a client and a server. The client handles the presentation layer, and the server manages the data layer. This model is typically seen in desktop applications where the user interface is on the user's machine, and the database is on a server. Communication usually occurs directly between the client and the server, which can be a database server with query-processing capabilities.

**Note:** In a typical web application, the client (browser) does not directly interact with the database server. Instead, the browser requests web pages from a **web server**, which in turn sends its response (HTML, CSS, JavaScript) back to the browser for rendering. The web server *may* interact with an application server or database in order to formulate it's response, but in general, the scenario of a person visiting a website does not constitute a Two-Tier Architecture.

#### Three-Tier Architecture

A `three-tier` architecture introduces an additional layer between the client and the database server, known as the application server. In this model, the client manages the presentation layer, the application server handles all the business logic and processing, and the third tier is a database server. This separation provides added flexibility and scalability because each layer can be developed and maintained independently.

#### N-Tier Architecture

In more complex systems, an `N-tier` architecture is used, where `N` refers to any number of separate tiers used beyond three. This setup involves multiple levels of application servers, each responsible for different aspects of business logic, processing, or data management. N-tier architectures are highly scalable and allow for distributed deployment, making them ideal for web applications and services that demand robust, flexible solutions.

### Hybrid Architecture

A `Hybrid` model blends elements of both `Client-Server` and `Peer-to-Peer (P2P)` architectures. In this setup, central servers are used to facilitate coordination and authentication tasks, while the actual data transfer occurs directly between peers. This combination leverages the strengths of both architectures to enhance efficiency and performance.
![[Hybrid_Architecture-1.webp]]
#### Advantage
- `Efficiency` Relieves workload from servers by letting peers share data.
- `Control` Central server can still manage user authentication, directory services, or indexing.
#### Disadvantage
- `Complex Implementation` Requires more sophisticated design to handle both centralized and distributed components.
- `Potential Single Point of Failure` If the central coordinating server fails, peer discovery might stop.
## [[Cloud|Cloud Architecture]]

`Cloud Architecture` refers to computing infrastructure that is hosted and managed by third-party providers, such as AWS, Azure, and Google Cloud. This architecture operates on a virtualized scale following a client-server model. It provides on-demand access to resources such as servers, storage, and applications, all accessible over the Internet. In this model, users interact with these services without controlling the underlying hardware.

![[Cloud_Arch-1.webp]]
#### Advantage
- `Scalability` Easily add or remove computing resources as needed.
- `Reduced cost & maintenance` Hardware managed by the cloud provider.
- `Flexibility` Access services from anywhere with Internet connectivity.
#### Disadvantage
- `Vendor lock-in` Migrating from one cloud provider to another can be complex.
- `Security/Compliance` Relying on a third party for data hosting can introduce concerns about data privacy.
- `Connectivity` Requires stable Internet access.
### Software-Defined Architecture (SDN)

`Software-Defined Networking (SDN)` is a modern networking approach that separates the control plane, which makes decisions about where traffic is sent, from the data plane, which actually forwards the traffic. 
Traditionally, network devices like routers and switches housed both of these planes. However, in SDN, the control plane is centralized within a software-based controller. This configuration allows network devices to simply execute instructions they receive from the controller.
SDN provides a programmable network management environment, enabling administrators to dynamically adjust network policies and routing as required. This separation makes the network more flexible and improves how it's managed.
![[Software-Defined_Arch-1.webp]]
#### Advantage
- `Centralized control` Simplifies network management.
- `Programmability & Automation Network` configurations can be changed quickly through software instead of manually configuring each device.
- `Scalability & Efficiency` Can optimize traffic flows dynamically, leading to better resource utilization.
#### Disadvantage
- `Controller Vulnerability` If the central controller goes down, the network might be adversely affected.
- `Complex Implementation` Requires new skill sets and specialized software/hardware.