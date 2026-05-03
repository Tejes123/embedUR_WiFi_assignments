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


## 3. Where this CAPWAP fits in OSI model, what are the two tunnels in CAPWAP and its purpose
## 4. Whats the difference between Lightweight APs and Cloud-based APs
## 5. How the CAPWAP tunnel is maintained between AP and controller
## 6. whats the difference between Sniffer and monitor mode , use case for each mode
## 7. If WLC deployed in WAN, which AP mode is best for local network and how?
## 8. What are challenges if deploying autonomous APs (more than 50) in large network like university
## 9. What happens on wireless client connected to Lightweight AP in local mode if WLC goes down.

