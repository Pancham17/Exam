# Complete Answer Key: Network Layer & Routing Protocols

This answer key is compiled based on the content of **Module 3.1** and **Module 3.2-1**.

---

## Continuous Assessment Test II (SET C) Answers

### Part A: Answer ALL the Questions. (5Q x 2M = 10M)

### 1. Define routing and differentiate static and dynamic routing.
* **Routing Definition:** Routing is the process of **determining the best path** for data to travel from the source to the destination across a network or interconnected networks. Routers use routing tables to make path selection decisions.
* **Differentiation:**

| Feature | **Static Routing** (Non-adaptive) | **Dynamic Routing** (Adaptive) |
| :--- | :--- | :--- |
| **Routing Table** | Manually configured; **does not change** automatically. | Changes **automatically** based on network topology changes. |
| **Algorithms** | Does not use complex routing algorithms. | Uses complex algorithms (e.g., RIP, OSPF). |
| **Security** | Provides higher security (manual control). | Lower security compared to static routing. |

### 2. What are the types of approaches available in packet switching?
1.  **Datagram Approach (Connectionless):** Each packet is treated **independently**. Packets may take different routes and can arrive out of order. No connection setup is required.
2.  **Virtual Circuit Approach (Connection-Oriented):** A **logical connection (Virtual Circuit)** is established before data transfer. All packets follow this single, predefined route, ensuring in-order delivery.

### 3. Explain the purpose of the Time to Live (TTL) field in an IPv4 datagram.
* **Purpose:** The TTL field (8 bits) controls the **maximum number of hops** (routers) an IPv4 datagram can pass through.
* **Need:** It prevents packets from circulating indefinitely (looping) in the network due to routing errors, thereby preventing network congestion.
* **Mechanism:** Every router **decrements the TTL value by one**. If the value reaches zero, the router **discards the datagram**.

### 4. Change the following IPv4 addresses from binary notation to dotted-decimal notation.
* **Binary:** `11000001 . 10000011 . 00011011 . 11111111`
* **Answer:** **193.131.27.255**

### 5. Change the following IPv4 addresses from dotted-decimal notation to binary notation.
* **Dotted-Decimal:** `221.34.7.82`
* **Answer:** **11011101 . 00100010 . 00000111 . 01010010**

---

### Part B: Answer any One Question. (1Q x 10M = 10M)

### 6. Compute the routing tables for each node after two iterations of the Distance Vector Routing algorithm.
The calculation uses the Bellman-Ford equation: $D_x(y) \leftarrow \min_v\{c(x,v) + D_v(y)\}$.

| Node | To A (Cost/Hop) | To B (Cost/Hop) | To C (Cost/Hop) | To D (Cost/Hop) | To E (Cost/Hop) | To F (Cost/Hop) | To G (Cost/Hop) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **A** | 0 (A) | 2 (B) | 10 (B/D) | 3 (D) | 7 (B) | 9 (B/D) | $\infty$ |
| **B** | 2 (A) | 0 (B) | 8 (E) | 5 (A) | 5 (E) | 7 (E) | 11 (E) |
| **C** | 10 (E) | 8 (E) | 0 (C) | 8 (E) | 3 (E) | 4 (F) | 3 (G) |
| **D** | 3 (A) | 5 (A) | 8 (E) | 0 (D) | 5 (E) | 7 (E) | 11 (E) |
| **E** | 7 (B) | 5 (B) | 3 (C) | 5 (D) | 0 (E) | 2 (F) | 6 (C/F) |
| **F** | 9 (E) | 7 (E) | 4 (C) | 7 (E) | 2 (E) | 0 (F) | 4 (G) |
| **G** | 13 (F) | 11 (C/F) | 3 (C) | 11 (F) | 6 (F) | 4 (F) | 0 (G) |

### 7. Compare and contrast Distance Vector Routing (DVR) and Link State Routing (LSR) algorithm.

| Feature | **Distance Vector Routing (e.g., RIP)** | **Link State Routing (e.g., OSPF)** |
| :--- | :--- | :--- |
| **Core Principle** | Shares **distance** to all destinations with **neighbors**. | Shares **link state** (neighbor info) with **all routers** via flooding. |
| **Knowledge** | Knows only its neighbors. | All routers have the **complete network topology**. |
| **Algorithm** | **Bellman-Ford Algorithm**. | **Dijkstra’s Algorithm** (Shortest Path First). |
| **Frequency** | **Periodic** updates (e.g., every 30 seconds). | **Event-driven** updates (only when topology changes). |
| **Convergence** | Slower, susceptible to "Count to Infinity." | Faster and more robust. |

---

## Continuous Assessment Test I (SET B) Answers

### Part A: Answer ALL the Questions. (5Q x 2M = 10M)

### 1. List the advantages of Network layer in OSI model.
* **Packetizing** service facilitates data transport.
* Eliminates **single points of failure** in data communication.
* Routers **reduce network traffic** by creating broadcast domains.
* Facilitates **Forwarding** and **Routing** of data packets.

### 2. Explain the Border Gateway Protocol (BGP).
* **BGP** is an **interdomain routing protocol** that uses the **path-vector routing** algorithm.
* It is used to exchange routing information **between different Autonomous Systems (AS)** (e.g., between different Internet Service Providers) on the global Internet.

### 3. What is the function of the Header Checksum field in IPv4?
* **Function:** The Header Checksum (16 bits) is used for **error detection in the IPv4 header** only.
* **Mechanism:** It ensures that critical header fields, such as the source and destination IP addresses, have not been corrupted during transmission, preventing misdelivery. If an error is detected, the router discards the datagram.

### 4. Change the following IPv4 addresses from binary notation to dotted-decimal notation.
* **Binary:** `10101100 . 00010000 . 00000000 . 00000001`
* **Answer:** **172.16.0.1**

### 5. Change the following IPv4 addresses from dotted-decimal notation to binary notation.
* **Dotted-Decimal:** `112.54.63.2`
* **Answer:** **01110000 . 00110110 . 00111111 . 00000010**

---

### Part B: Answer any One Question. (1Q x 10M = 10M)

### 6. Explain the following concepts: a) Open Shortest Path First (OSPF), b) Routing Information Protocol (RIP).
**a. Open Shortest Path First (OSPF)**
* **Type:** Link-State routing protocol, Interior Gateway Protocol (IGP).
* **Mechanism:** OSPF routers share Link-State Advertisements (LSAs) with **all** other routers in the Autonomous System (AS).
* **Algorithm:** Uses **Dijkstra’s Algorithm** (Shortest Path First) to calculate the least-cost path.
* **Metric:** Uses a **cost metric** based on factors like bandwidth, not just hop count.

**b. Routing Information Protocol (RIP)**
* **Type:** Distance-Vector routing protocol, Interior Gateway Protocol (IGP).
* **Mechanism:** Routers **periodically broadcast their entire routing table** to their **directly connected neighbors** (e.g., every 30 seconds).
* **Metric:** Uses simple **hop count**, with a maximum count of **15** (16 is infinity).
* **Loop Prevention:** Uses **split horizon** and **route poisoning**.

### 7. With a neat diagram, explain the structure of an IPv4 datagram.
An IPv4 datagram consists of a **Header** (20 to 60 bytes) and a **Payload (Data)**.

| Field | Length (bits) | Function |
| :--- | :--- | :--- |
| **Version** | 4 | Identifies the IP version (currently 4). |
| **Header Length (HLEN)** | 4 | Length of the header in 4-byte words (min 5, max 15). |
| **Total Length** | 16 | Total length of the datagram (header + data) in bytes. |
| **Time to Live (TTL)** | 8 | Prevents looping; decremented at each hop. |
| **Protocol** | 8 | Identifies the higher-layer protocol (e.g., TCP or UDP). |
| **Header Checksum** | 16 | Used for error detection in the header. |
| **Source Address** | 32 | IP address of the sending host. |
| **Destination Address** | 32 | IP address of the receiving host. |
| **Options** | 0-320 | Optional field for debugging or security. |



---

## Continuous Assessment Test II (SET A) Answers

### Part A: Answer ALL the Questions. (5Q x 2M = 10M)

### 1. Define routing.
* **Routing** is the process where a router determines the **most efficient or optimal path** for a data packet to travel from its source network to its destination network.

### 2. Differentiate static routing and dynamic routing.
* **Differentiation:** (See table provided in SET C, Q1).

### 3. List the role of Network layer in OSI model.
* **Routing:** Determining the best path for data packets.
* **Forwarding:** Transferring packets from one node to the next.
* **Logical Addressing:** Translating logical addresses (IP) to physical addresses (MAC).
* **Fragmentation:** Breaking down large packets for transmission.

### 4. Change the following IPv4 addresses from binary notation to dotted-decimal notation.
* **Binary:** `11000000 . 10101000 . 00101010 . 00000010`
* **Answer:** **192.168.42.2**

### 5. Change the following IPv4 addresses from dotted-decimal notation to binary notation.
* **Dotted-Decimal:** `96.19.69.10`
* **Answer:** **01100000 . 00010011 . 01000101 . 00001010**

---

### Part B: Answer any One Question. (1Q x 10M = 10M)

### 6. Explain how the Distance Vector Routing (DVR) algorithm updates routing tables in a network. What information is exchanged, and how often?
* **Update Mechanism:** DVR uses the **Bellman-Ford equation** to calculate the minimum cost to all destinations. A node updates its distance $D_x(y)$ by checking the minimum cost via its neighbors ($v$): $D_x(y) \leftarrow \min_v\{c(x,v) + D_v(y)\}$.
* **Information Exchanged:** Each router exchanges its **entire Distance Vector (its routing table)** with its **directly connected neighbors**.
* **Frequency:** The exchange occurs **periodically** at regular, fixed intervals (e.g., every 30 seconds for RIP).

### 7. Explain the concept of packet switching in Network Layer and also explain approaches/types of packet switching.
* **Concept of Packet Switching:** Data is divided into small, independent units called **packets**. It uses a **Store and Forward** approach at each hop. It does not reserve a dedicated path, maximizing bandwidth efficiency.
* **Approaches/Types of Packet Switching:**
    1.  **Datagram Approach (Connectionless):** No setup phase. Packets are routed independently and may take different paths.
    2.  **Virtual Circuit Approach (Connection-Oriented):** Requires a **Setup** phase to establish a logical path. All packets follow the same path during the **Data Transfer** phase, followed by a **Tear Down** phase.
