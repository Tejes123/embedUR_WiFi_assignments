# Module 2 - Assignment answers

## 1. Brief about SplitMAC architecture and how it improves the AP's performance

## SplitMAC Architecture and its Impact on AP Performance

SplitMAC is an architectural model used in centralized wireless networks (commonly with controller-based systems) where the functionality of the MAC layer (from IEEE 802.11) is **split between the Access Point (AP) and a Wireless LAN Controller (WLC)**.


### 1. Concept of SplitMAC

SplitMAC divides the MAC layer into two parts:

* **Lower MAC (LMAC)** → handled by the AP
* **Upper MAC (UMAC)** → handled by the controller

The AP performs time-critical and real-time operations, while the controller handles **decision-making and management tasks**.


### 2. Functions handled by the AP (Lower MAC)

The AP is responsible for operations that require immediate response:

1. Frame transmission and reception
2. Acknowledgment (ACK) handling
3. Retransmissions
4. Encryption/decryption (in many implementations)
5. Real-time medium access (CSMA/CA timing)

These tasks must happen locally to meet strict timing constraints of wireless communication.


### 3. Functions handled by the Controller (Upper MAC)

1. Authentication and association management
2. Roaming decisions
3. QoS policy enforcement
4. Security policies (WPA2/WPA3, access control)
5. RF management and channel selection
6. Load balancing across APs

The controller centralizes intelligence and network control.

### 4. Communication between AP and Controller

* Communication happens using protocols like **CAPWAP**
* Data and control messages are tunneled between AP and WLC
* The AP acts as a **lightweight device**, while the controller acts as the **brain of the network**


### 5. How SplitMAC improves AP performance

1. **Reduced Processing Load on AP**
   Since complex decision-making is offloaded to the controller, the AP requires less CPU and memory, allowing it to focus on real-time wireless operations.

2. **Faster Real-time Response**
   Time-sensitive tasks (ACKs, retransmissions) are handled locally, ensuring compliance with strict timing requirements of wireless protocols.

3. **Centralized Optimization**
   The controller has a global view of the network and can optimize:

   * Channel allocation
   * Power levels
   * Client distribution

4. **Efficient Roaming**
   Faster handoff between APs because the controller manages client state centrally.

5. **Scalability**
   Large networks can be managed easily since multiple APs are controlled centrally without complex configuration on each AP.

6. **Simplified AP Design**
   APs become lightweight devices, reducing cost and complexity.


### 6. Overall Impact

SplitMAC architecture transforms the AP from a fully independent device into a **distributed radio unit**, while the controller becomes the **central intelligence layer**, resulting in:

* Better performance in dense deployments
* Improved network efficiency
* Easier management and scalability


## 2. Describe about CAPWAP, explain the flow between AP and Controller

## CAPWAP and the Flow Between AP and Controller

CAPWAP (**Control And Provisioning of Wireless Access Points**) is a protocol used to enable communication between a **lightweight Access Point (AP)** and a **Wireless LAN Controller (WLC)** in centralized Wi-Fi networks based on IEEE 802.11.

It allows the AP to offload control and management functions to the controller while maintaining data forwarding through a secure tunnel.

---

## 1. Purpose of CAPWAP

1. Provides a **standardized way** for APs to join and be managed by a controller
2. Enables **centralized configuration and monitoring**
3. Establishes **secure tunnels** for control and data traffic
4. Supports **SplitMAC architecture** by separating control and data functions

---

## 2. CAPWAP Tunnel Types

1. **Control Tunnel**

   * Used for management messages
   * Handles configuration, authentication, keepalives

2. **Data Tunnel**

   * Carries client data traffic between AP and controller
   * May be enabled or disabled depending on deployment (local vs central switching)


## 3. CAPWAP Flow Between AP and Controller

When an AP boots up, it follows a sequence of steps to connect to the controller:

### 1. AP Initialization

* AP powers on and initializes hardware
* Gets IP address using DHCP


### 2. Controller Discovery

* AP discovers the WLC using:

  * DHCP option
  * DNS resolution
  * Preconfigured IP
  * Broadcast (in same subnet)


### 3. CAPWAP Discovery Request

* AP sends **Discovery Request** messages to potential controllers
* Controllers respond with **Discovery Response**


### 4. Controller Selection

* AP selects a controller based on:

  * Load
  * Priority
  * Configuration


### 5. CAPWAP Join Phase

* AP sends a **Join Request**
* Controller replies with **Join Response**
* AP is now logically connected to the WLC


### 6. Authentication and Security Setup

* DTLS (Datagram TLS) is established
* Ensures secure communication between AP and controller


### 7. Configuration Download

* AP downloads configuration from controller:

  * SSID
  * Security policies
  * Channel and power settings


### 8. CAPWAP Tunnel Establishment

* Two tunnels are created:

  1. Control tunnel (management)
  2. Data tunnel (client traffic, if centralized)


### 9. Operational Phase

* AP starts serving clients
* Client traffic flow:

  * **Centralized mode**: Client → AP → Controller → Network
  * **Local mode**: Client → AP → Local network


### 10. Keepalive / Heartbeat

* AP periodically sends keepalive messages
* Ensures controller connectivity
* If lost, AP attempts reconnection

## 4. Data Flow Example

### Control Plane Flow

* AP ↔ WLC:

  * Configuration updates
  * Client association info
  * Monitoring and statistics

### Data Plane Flow

* Client → AP → (CAPWAP tunnel) → WLC → Network
* Or locally switched depending on configuration


## 5. Advantages of CAPWAP

1. Centralized management of multiple APs
2. Simplified deployment and configuration
3. Improved security via encrypted tunnels
4. Scalability for large networks
5. Efficient roaming support



## 3. Where this CAPWAP fits in OSI model, what are the two tunnels in CAPWAP and its purpose

## CAPWAP in OSI Model and Its Tunnels

### 1. Where CAPWAP fits in the OSI model

CAPWAP operates primarily at the **upper layers of the OSI model**, with the following mapping:

1. **Application Layer (Layer 7)**
   CAPWAP itself is an application-layer protocol that defines how an Access Point (AP) communicates with a Wireless LAN Controller (WLC).

2. **Transport Layer (Layer 4)**
   CAPWAP uses **UDP** for transport:

   * UDP Port **5246** → Control traffic
   * UDP Port **5247** → Data traffic

3. **Network Layer (Layer 3)**
   Runs over IP (IPv4/IPv6) for routing between AP and controller.

4. **Security Layer (Overlay)**
   Uses **DTLS (Datagram TLS)** over UDP to provide encryption and integrity.

Overall view:
CAPWAP = Application layer protocol running over UDP/IP with DTLS security.

---

### 2. CAPWAP Tunnels

CAPWAP establishes two logical tunnels between the AP and the controller:

---

#### 2.1 Control Tunnel

**Purpose: Management and control communication**

Functions:

1. AP discovery and join process
2. Configuration download (SSID, security, RF parameters)
3. Authentication between AP and controller
4. Keepalive/heartbeat messages
5. Monitoring and statistics exchange

Characteristics:

* Always established
* Typically **encrypted using DTLS**
* Uses UDP port **5246**

---

#### 2.2 Data Tunnel

**Purpose: Transport of client data traffic**

Functions:

1. Carries user data (client packets)
2. Encapsulates 802.11 frames into CAPWAP format
3. Forwards traffic between AP and controller

Characteristics:

* Uses UDP port **5247**
* May be **enabled or disabled** depending on deployment:

  * **Central switching** → data goes through controller
  * **Local switching** → data bypasses controller

---

### 3. Summary Table

| Tunnel Type | Purpose                  | Traffic Type     | Encryption | UDP Port |
| ----------- | ------------------------ | ---------------- | ---------- | -------- |
| Control     | Management and signaling | AP ↔ Controller  | Yes (DTLS) | 5246     |
| Data        | Client data forwarding   | Client ↔ Network | Optional   | 5247     |



## 4. Whats the difference between Lightweight APs and Cloud-based APs 

## Difference between Lightweight APs and Cloud-based APs

| Feature                     | Lightweight AP (Controller-based)                                  | Cloud-based AP                                           |
|-----------------------------|--------------------------------------------------------------------|----------------------------------------------------------|
| Definition                  | AP that depends on an on-premise Wireless LAN Controller (WLC)     | AP managed through a cloud-hosted controller/platform     |
| Architecture                | Centralized (on-site controller)                                   | Cloud-managed (controller hosted in cloud)               |
| Control Plane               | Handled by local WLC                                               | Handled by cloud controller                              |
| Data Plane                  | Can be centrally switched or locally switched                      | Usually locally switched (data stays in local network)    |
| Deployment Requirement      | Requires physical WLC in network                                   | No on-prem controller required                           |
| Management                  | Managed via WLC interface                                          | Managed via web portal/dashboard over internet            |
| Scalability                 | Limited by controller capacity                                     | Highly scalable (cloud resources)                        |
| Initial Cost                | Higher (controller hardware required)                              | Lower upfront (subscription-based)                       |
| Maintenance                 | Requires maintenance of WLC hardware/software                      | Managed by vendor (automatic updates)                    |
| Internet Dependency         | Not required for local operation                                   | Requires internet for management access                  |
| Configuration               | Centralized but tied to WLC                                        | Centralized and accessible from anywhere                 |
| Firmware/Updates            | Manually managed via controller                                    | Automatic updates via cloud                              |
| Roaming                     | Efficient (controller-assisted roaming)                            | Efficient (cloud-coordinated, vendor-dependent)          |
| Use Case                    | Enterprises, campuses with strict control                          | Distributed networks, SMBs, remote site management        |

---



## 5. How the CAPWAP tunnel is maintained between AP and controller 

## How the CAPWAP Tunnel is Maintained Between AP and Controller

CAPWAP maintains a reliable and secure connection between the Access Point (AP) and Wireless LAN Controller (WLC) through continuous signaling, security mechanisms, and state management.

---

### 1. Establishment of Secure Session

After the AP joins the controller, a **DTLS (Datagram Transport Layer Security)** session is established over UDP.
This ensures:

1. Encryption of control traffic
2. Integrity of messages
3. Authentication between AP and controller

This secure session forms the base for maintaining the CAPWAP tunnel.

---

### 2. Periodic Keepalive Messages

The AP and controller exchange **keepalive (heartbeat) messages** at regular intervals.

1. AP sends keepalive requests to WLC
2. WLC responds with acknowledgments
3. Confirms that both ends are active and reachable

If responses are not received within a timeout:

* The tunnel is considered **down**
* Recovery procedures are triggered

---

### 3. CAPWAP Control Messages

The control tunnel continuously carries management messages such as:

1. Configuration updates
2. Client association information
3. Statistics and monitoring data

This constant exchange ensures the session remains active and synchronized.

---

### 4. Sequence Numbers and Timers

CAPWAP uses:

1. **Sequence numbers** → to track packets and detect loss
2. **Timers** → to detect inactivity or failure

If packets are lost or delayed beyond thresholds:

* Retransmissions or recovery actions are initiated

---

### 5. Data Tunnel Maintenance

For deployments using centralized switching:

1. Data packets are encapsulated in CAPWAP
2. Continuous traffic flow helps keep the tunnel active
3. If idle, control keepalives still maintain the session

---

### 6. Reconnection Mechanism

If the tunnel is disrupted:

1. AP detects loss of keepalive responses
2. Tears down the existing session
3. Re-initiates:

   * Discovery
   * Join process
4. Re-establishes CAPWAP tunnels

---

### 7. NAT Traversal Support

CAPWAP supports operation across NAT:

1. Uses UDP (ports 5246/5247)
2. Periodic traffic keeps NAT bindings alive
3. Ensures connectivity even across different networks

---

### 8. Controller Redundancy (Optional)

In enterprise deployments:

1. AP maintains knowledge of **primary and backup controllers**
2. If primary fails:

   * AP switches to secondary controller
   * Re-establishes tunnel automatically



## 6. whats the difference between Sniffer and monitor mode , use case for each mode 

## Difference between Sniffer Mode and Monitor Mode (Wi-Fi)

| Feature                     | Monitor Mode                                                     | Sniffer Mode                                                      |
|----------------------------|------------------------------------------------------------------|-------------------------------------------------------------------|
| Definition                 | A NIC mode that allows capturing all wireless frames in the air | A usage/role where traffic is captured and analyzed               |
| Level                      | Driver/firmware level (interface operating mode)                 | Application/analysis level (uses capture tools)                   |
| Frame Visibility           | Captures raw 802.11 frames (management, control, data)          | Depends on mode; typically uses monitor mode to get full frames   |
| Requirement                | Must be enabled on the wireless interface                        | Requires a capture tool (e.g., packet analyzer)                   |
| Association with AP        | Not associated to any AP while capturing                         | May or may not be associated (tool-dependent)                     |
| Channel Handling           | Usually fixed to one channel (can be switched manually/hopping)  | Follows the underlying interface (often monitor mode)             |
| Header Information         | Includes full 802.11 headers and radio metadata (RSSI, channel)  | Shows decoded packets; detail depends on capture configuration    |
| Typical Tools              | `iw`, `airmon-ng` to enable                                      | Wireshark, tcpdump, Kismet                                        |
| Purpose                    | Enable raw packet capture from the wireless medium               | Analyze captured traffic for debugging/security                   |

---

### Explanation

**Monitor Mode**
1. Puts the Wi-Fi interface into a passive listening state.  
2. The NIC captures every frame on the channel, including management and control frames defined in the Wi-Fi standard.  
3. The device is not connected to any network during capture.  
4. Provides low-level visibility needed for protocol analysis.

**Sniffer Mode**
1. Refers to the act of capturing and analyzing packets using software tools.  
2. Relies on monitor mode (for Wi-Fi) to obtain full 802.11 frames.  
3. Decodes frames into human-readable form for troubleshooting or analysis.  
4. Can also be used in wired networks without monitor mode.

---

### Use Cases

**Monitor Mode**
1. Wireless troubleshooting at frame level  
2. RF analysis and channel utilization study  
3. Security auditing (detecting rogue APs, attacks)  
4. Capturing management/control frames (beacons, probes, ACKs)

**Sniffer Mode**
1. Packet analysis using tools like Wireshark  
2. Debugging connectivity or protocol issues  
3. Performance analysis (latency, retransmissions)  
4. Network security monitoring and intrusion detection  



## 7. If WLC deployed in WAN, which AP mode is best for local network and how? 

### If WLC is Deployed in WAN, Which AP Mode is Best for Local Network and How?

When the Wireless LAN Controller (WLC) is located across a WAN (remote/cloud), the **best AP mode for the local network is FlexConnect mode (also called H-REAP in older systems)**.

---

### 1. Why FlexConnect Mode is Best

1. In WAN deployments, sending all client data to a remote WLC introduces:

   * Higher latency
   * Bandwidth consumption
   * Dependency on WAN availability

2. FlexConnect allows the AP to:

   * **Switch client data locally**
   * Use the WLC only for **control and management**

3. This reduces WAN dependency and improves performance for local users.

---

### 2. How FlexConnect Works

1. AP establishes a **CAPWAP control tunnel** to the WLC over WAN

2. Configuration (SSID, security policies) is downloaded from WLC

3. Client traffic handling:

   * **Local Switching**:
     Client → AP → Local LAN (does not go to WLC)
   * **Central Switching (optional)**:
     Client → AP → WLC → Network

4. Authentication:

   * Can be handled centrally (via WLC/RADIUS)
   * Or locally (cached credentials for survivability)

---

### 3. Key Advantages in WAN Scenario

1. **Reduced Latency**
   Data does not traverse WAN for local communication

2. **Bandwidth Efficiency**
   WAN is not burdened with user data traffic

3. **WAN Failure Resilience**

   * Clients can still access local network resources
   * AP can continue functioning with cached configuration

4. **Scalability**
   Multiple remote sites can be managed centrally

---

### 4. Comparison with Local Mode (Why not Local Mode)

* In **Local Mode AP**:

  * All client traffic is tunneled to WLC
  * Not suitable when WLC is in WAN
  * Leads to:

    * Increased latency
    * WAN congestion
    * Dependency on controller availability

### 5. Conclusion

FlexConnect mode is ideal when the WLC is deployed in WAN because it allows **centralized control with local data forwarding**, ensuring better performance, reduced latency, and continued operation even during WAN disruptions.


## 8. What are challenges if deploying autonomous APs (more than 50) in large network like university 

## Challenges of Deploying Autonomous APs in Large Networks (e.g., University)

In a large-scale environment, using **autonomous (fat) APs** based on IEEE 802.11 introduces several operational and performance challenges due to the lack of centralized control.

---

### 1. Configuration Complexity

1. Each AP must be configured **individually**
2. Managing SSIDs, security, VLANs across 50+ APs is time-consuming
3. High risk of **configuration inconsistencies**

---

### 2. Poor Scalability

1. No centralized management system
2. Adding new APs increases operational overhead linearly
3. Difficult to maintain uniform network behavior at scale

---

### 3. Inefficient RF Management

1. Channel and transmit power are set **locally per AP**
2. No global optimization → leads to:

   * Co-channel interference
   * Overlapping channels
3. Performance degrades in dense deployments

---

### 4. Roaming Issues

1. No centralized client tracking
2. Devices experience **delayed or inefficient roaming**
3. Possible connection drops during movement across campus

---

### 5. Security Management Challenges

1. Policies must be configured on each AP
2. Hard to enforce **uniform security (WPA2/WPA3, ACLs)**
3. Difficult to detect rogue APs or threats centrally

---

### 6. Monitoring and Troubleshooting Difficulty

1. No single dashboard for network visibility
2. Requires logging into each AP separately
3. Hard to diagnose network-wide issues

---

### 7. Firmware and Updates Management

1. Updates must be done **manually per AP**
2. Time-consuming and error-prone
3. Risk of version mismatch across APs

---

### 8. Load Balancing Limitations

1. No centralized control of client distribution
2. Some APs may become overloaded while others are underutilized
3. Leads to uneven performance

---

### 9. Lack of Advanced Features

1. Limited support for:

   * Seamless roaming (fast roaming)
   * Centralized QoS
   * RF optimization algorithms
2. Cannot leverage enterprise-grade optimizations

---

### 10. Operational Cost and Effort

1. Increased administrative effort
2. Higher maintenance cost over time
3. Requires more manual intervention for daily operations

---

### Conclusion

Deploying more than 50 autonomous APs in a large environment like a university leads to **management complexity, poor scalability, inefficient RF utilization, and inconsistent performance**, making controller-based architectures more suitable.

## 9. What happens on wireless client connected to Lightweight AP in local mode if WLC goes down.

## What happens to a wireless client when WLC goes down (Lightweight AP in Local Mode)

In **Local Mode**, a lightweight AP relies on the controller for both control and (typically) data forwarding over a CAPWAP tunnel. If the WLC becomes unavailable, the impact on clients is immediate.

---

### 1. Loss of CAPWAP Connectivity

1. The AP detects loss of the CAPWAP control tunnel (keepalives fail).
2. Since Local Mode depends on the controller, the AP cannot continue normal operation.

---

### 2. Existing Client Sessions

1. Client data traffic (which is tunneled to the WLC) stops.
2. Active sessions are **interrupted/dropped**.
3. Applications lose connectivity to network/internet resources.

---

### 3. New Client Connections

1. The AP cannot process new authentication/association without the WLC.
2. New clients **cannot join** the network.

---

### 4. AP Behavior

1. The AP may stop serving clients and enter a **disconnected state**.
2. It attempts to:

   * Reconnect to the same controller, or
   * Discover and join a backup controller (if configured)

---

### 5. Roaming Impact

1. Roaming between APs fails because client state is maintained at the controller.
2. Clients may disconnect during movement.

---

### 6. No Local Switching (Key Limitation)

1. In Local Mode, traffic is centrally switched via the WLC.
2. Without WLC, **no local data forwarding occurs**.
3. Even local LAN access is unavailable.

---

### 7. Recovery Scenario

1. If a **secondary/backup WLC** is configured:

   * AP joins the backup controller
   * Clients reconnect after reassociation
2. If no backup:

   * Service remains down until WLC is restored

