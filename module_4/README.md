# Assignment 4

## 1. What is the significance of MAC layer and in which position it is placed in the OSI model

1. The MAC (Medium Access Control) layer is a sublayer of the **Data Link Layer (Layer 2)** in the OSI model. It operates above the PHY layer and below higher networking layers.
2. Its primary significance lies in controlling how devices share and access the wireless medium, which is inherently **shared and contention-based**.
3. In Wi-Fi (IEEE 802.11), multiple devices transmit over the same channel. The MAC layer ensures orderly communication using mechanisms like **CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)**.
4. It determines **when a device can transmit**, reducing collisions and improving efficiency.
5. The MAC layer is responsible for **framing**, meaning it encapsulates higher-layer data into structured frames for transmission.
6. It handles **addressing**, using MAC addresses to identify source and destination devices.
7. Reliability is ensured through **acknowledgments (ACKs)** and retransmissions in case of packet loss.
8. It also manages **fragmentation and reassembly**, which helps transmit large frames over unreliable channels.
9. Power-saving mechanisms are supported, allowing devices to enter low-power states when inactive.
10. Security functions like **encryption and authentication (WPA/WPA2/WPA3)** are coordinated at the MAC layer.
11. It plays a crucial role in **mobility**, enabling seamless roaming between access points.
12. Overall, the MAC layer acts as the **intelligence layer** that coordinates communication over the physical medium, ensuring efficiency, fairness, and reliability.

---

## 2. Describe the frame format of the 802.11 MAC header and explain the purpose of each fields

1. The 802.11 MAC frame consists of **Header, Payload, and Frame Check Sequence (FCS)**.
2. The MAC header is typically 24–30 bytes (can extend to 36 bytes).

### Key fields in MAC header:

1. **Frame Control (2 bytes)**

   * Contains subfields: protocol version, type (Management/Control/Data), subtype, flags (To DS, From DS, Retry, Power Management, etc.).
2. **Duration/ID (2 bytes)**

   * Indicates how long the channel will be reserved (used for NAV – Network Allocation Vector).
3. **Address fields (6 bytes each)**

   * Up to four addresses:

     * Source Address (SA)
     * Destination Address (DA)
     * Transmitter Address (TA)
     * Receiver Address (RA)
   * Used for routing in infrastructure and ad hoc modes.
4. **Sequence Control (2 bytes)**

   * Contains sequence number and fragment number.
   * Helps in ordering and reassembly.
5. **QoS Control (optional, 2 bytes)**

   * Used in QoS-enabled networks (802.11e).
   * Defines traffic priority.
6. **HT/VHT/HE Control (optional)**

   * Used in advanced standards for additional PHY-related control.

### Other parts:

1. **Payload**

   * Carries upper-layer data (IP packet, etc.).

2. **FCS (4 bytes)**

   * Error detection using CRC.

3. The MAC header enables proper delivery, sequencing, prioritization, and control of wireless frames.

---

## 3. Please list all the MAC layer functionalities in all Management, Control and Data plane

### 1. Management Plane Functions

1. Scanning (active/passive)
2. Beacon transmission
3. Authentication and deauthentication
4. Association and reassociation
5. Disassociation
6. Roaming support
7. Network discovery and synchronization
8. Power management coordination
9. Security management (key exchange, authentication)

---

### 2. Control Plane Functions

1. RTS/CTS (Request to Send / Clear to Send)
2. ACK (Acknowledgment) handling
3. Block ACK (for aggregated frames)
4. NAV (Network Allocation Vector) management
5. Inter-frame spacing (IFS control)
6. Contention window and backoff algorithm
7. Frame retransmission control
8. Collision avoidance mechanisms

---

### 3. Data Plane Functions

1. Data frame transmission and reception
2. Frame encapsulation and decapsulation
3. Fragmentation and reassembly
4. QoS handling (traffic prioritization)
5. Frame aggregation (A-MPDU, A-MSDU)
6. Error detection and correction coordination
7. Throughput optimization
8. Handling unicast, multicast, and broadcast traffic


## 4. Explain the scanning process and its types in detail

1. Scanning is the process by which a Wi-Fi client discovers available networks (Access Points).

### Types of scanning:

### 1. Passive Scanning

1. The client listens for **beacon frames** periodically sent by APs.
2. Each beacon contains SSID, supported rates, capabilities, etc.
3. The client switches channels and listens on each one.
4. Advantages:

   * Low power consumption
   * No additional traffic generated
5. Disadvantages:

   * Slower discovery


### 2. Active Scanning

1. The client actively sends **Probe Request** frames.
2. APs respond with **Probe Response** frames.
3. Faster than passive scanning.
4. Advantages:

   * Quick network discovery
   * Useful for hidden SSIDs
5. Disadvantages:

   * Higher power consumption
   * More channel traffic


### Scanning process steps:

1. Client selects channels to scan.
2. Performs passive or active scanning.
3. Collects AP information (RSSI, SSID, capabilities).
4. Builds a list of available networks.
5. Selects the best AP based on signal strength and policies.


## 5. Brief about the client association process

1. The association process connects a client (STA) to an Access Point (AP).

### Steps involved:

1. **Scanning**

   * Client discovers available APs.

2. **Authentication**

   * Client sends Authentication Request.
   * AP responds with Authentication Response.
   * Can be open or secure (WPA2/WPA3).

3. **Association**

   * Client sends Association Request (includes capabilities, supported rates).
   * AP replies with Association Response (assigns Association ID – AID).

4. **4-Way Handshake (Security)**

   * Establishes encryption keys (in WPA2/WPA3).

5. **Data Transfer Begins**

   * Client can now send/receive data frames.

---

### Additional aspects:

1. **Reassociation**

   * Occurs during roaming between APs.

2. **Disassociation/Deauthentication**

   * Terminates connection.

3. **Power Save Mode**

   * Client can negotiate sleep/wake cycles with AP.

---

### Summary:

* Association establishes logical connectivity.
* It ensures authentication, capability negotiation, and secure communication before data transfer.


## 6. Explain each steps involved in EAPOL 4-way handshake and the purpose of each keys derived from the process

1. The EAPOL 4-way handshake is used in WPA2/WPA3 to securely derive encryption keys between a client (STA) and Access Point (AP). It occurs after authentication.
2. It is based on a shared **PMK (Pairwise Master Key)** derived from a password or authentication server.

### Steps in the 4-way handshake:

1. **Message 1 (AP → STA)**

   1. AP sends a random nonce (**ANonce**).
   2. Purpose: Initiates handshake and provides randomness.

2. **Message 2 (STA → AP)**

   1. STA generates its own nonce (**SNonce**).
   2. Computes **PTK (Pairwise Transient Key)** using PMK, ANonce, SNonce, and MAC addresses.
   3. Sends SNonce and MIC (Message Integrity Code).

3. **Message 3 (AP → STA)**

   1. AP computes PTK using same inputs.
   2. Verifies MIC from STA.
   3. Sends **GTK (Group Temporal Key)** encrypted and installs keys.

4. **Message 4 (STA → AP)**

   1. STA acknowledges installation of keys.
   2. Handshake completes.

---

### Keys derived:

1. **PMK (Pairwise Master Key)**

   1. Root key derived from password or authentication.

2. **PTK (Pairwise Transient Key)**

   1. Session-specific key used for unicast encryption.
   2. Split into:

     * KCK (Key Confirmation Key) → integrity of messages
     * KEK (Key Encryption Key) → encrypts GTK
     * TK (Temporal Key) → encrypts data

3. **GTK (Group Temporal Key)**

   * Used for multicast/broadcast traffic.

---

### Purpose:

1. Ensures mutual authentication.
2. Prevents replay attacks using nonces.
3. Dynamically generates secure session keys.

---

## 7. Describe the power saving scheme in MAC layer and explore the types of Power saving mechanisms

1. Power saving in Wi-Fi MAC layer allows devices to conserve battery by reducing radio usage.
2. Managed using coordination between STA and AP.

---

### Basic Power Save Mode (PSM)

1. STA informs AP it is entering sleep mode.
2. AP buffers frames destined for STA.
3. STA wakes periodically to listen to **Beacon frames**.
4. Beacon contains **TIM (Traffic Indication Map)** indicating pending data.
5. STA sends PS-Poll or trigger to retrieve buffered data.

---

### Types of power saving mechanisms:

1. **Legacy Power Save (PSM)**

   * Uses PS-Poll frames.
   * Simple but inefficient for high traffic.

2. **U-APSD (Unscheduled Automatic Power Save Delivery)**

   * STA sends trigger frames.
   * AP delivers buffered packets in bursts.
   * Used in VoIP and multimedia.

3. **WMM Power Save**

   * Enhances QoS-aware power saving.

4. **Target Wake Time (TWT) – 802.11ax**

   * STA and AP agree on specific wake times.
   * Reduces contention and improves battery life.

---

### Benefits:

1. Reduces power consumption significantly.
2. Extends battery life in mobile devices.

### Trade-offs:

1. Increased latency.
2. Complexity in scheduling.

---

## 8. Describe the Medium Access Control methodologies

1. Wi-Fi uses contention-based and controlled access methods to share the medium.

---

### 1. CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)

1. Device senses channel before transmission.
2. If idle → transmit.
3. If busy → wait and perform **random backoff**.
4. Reduces collisions in wireless medium.

---

### 2. Inter Frame Spacing (IFS)

1. Different wait times define priority:

   * SIFS (Short IFS) → highest priority
   * DIFS (Distributed IFS)
   * PIFS (Point IFS)

---

### 3. Backoff Algorithm

1. Random delay before transmission.
2. Contention window increases after collisions.

---

### 4. RTS/CTS Mechanism

1. Used to avoid hidden node problem.
2. RTS → request to transmit
3. CTS → clear to transmit

---

### 5. Polling-based access (PCF – optional)

1. AP controls transmission.
2. Rarely used in practice.

---

### Summary:

1. Ensures fair and efficient medium sharing.
2. Balances throughput and collision avoidance.

---

## 9. Brief about the Block ACK mechanism and its advantages

1. Block ACK improves efficiency by acknowledging multiple frames at once.

---

### Working:

1. Sender transmits a burst of frames (A-MPDU).
2. Receiver sends a **Block ACK** instead of individual ACKs.
3. Block ACK contains bitmap indicating received frames.
4. Sender retransmits only missing frames.

---

### Types:

1. **Immediate Block ACK** → sent right after reception
2. **Delayed Block ACK** → sent later

---

### Advantages:

1. Reduces overhead (fewer ACK frames).
2. Improves throughput significantly.
3. Efficient retransmission (only lost frames).
4. Works well with frame aggregation.

---

### Use cases:

1. High-speed Wi-Fi (802.11n/ac/ax).
2. Bulk data transfer.

---

## 10. Explain about A-MSDU, A-MPDU and A-MSDU in A-MPDU

1. Frame aggregation combines multiple frames to improve efficiency.

---

### 1. A-MSDU (Aggregated MAC Service Data Unit)

1. Combines multiple MSDUs into one MPDU.
2. Single MAC header for all subframes.
3. Lower overhead but less robust.
4. If error occurs → entire frame retransmitted.

---

### 2. A-MPDU (Aggregated MAC Protocol Data Unit)

1. Combines multiple MPDUs.
2. Each MPDU has its own MAC header and FCS.
3. More robust (selective retransmission possible).
4. Works with Block ACK.

---

### 3. A-MSDU within A-MPDU

1. Hybrid aggregation technique.
2. Multiple MSDUs form A-MSDU.
3. Multiple A-MSDUs packed into A-MPDU.
4. Combines efficiency and reliability.

---

### Comparison:

| Feature         | A-MSDU      | A-MPDU    |
| --------------- | ----------- | --------- |
| Header overhead | Low         | Higher    |
| Error handling  | Poor        | Good      |
| Retransmission  | Whole frame | Selective |
| Efficiency      | High        | Moderate  |

---

### Benefits:

1. Reduces protocol overhead.
2. Increases throughput.
3. Essential for high-speed Wi-Fi.


