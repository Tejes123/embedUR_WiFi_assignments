

# Module 5 – Assignment Questions

## 1. What are the key features of Wi-Fi 6, 6E and 7 and how do they differ from previous standards like Wi-Fi 5 (802.11ac)?

1. **Wi-Fi 5 (802.11ac)** primarily operates in the 5 GHz band and introduces features like 256-QAM, wider channels (80/160 MHz), and MU-MIMO (downlink only). It focuses mainly on increasing peak data rates.
2. **Wi-Fi 6 (802.11ax)** improves both efficiency and performance in dense environments. Key features include:

   1. OFDMA for multi-user access.
   2. Uplink and downlink MU-MIMO.
   3. 1024-QAM for higher data rates.
   4. Target Wake Time (TWT) for power efficiency.
   5. Better performance in congested networks.
3. **Wi-Fi 6E** extends Wi-Fi 6 into the 6 GHz band, adding:

   1. More spectrum availability.
   2. Additional non-overlapping channels.
   3. Reduced interference compared to 2.4 GHz and 5 GHz.
4. **Wi-Fi 7 (802.11be)** introduces next-generation enhancements:

   1. 4096-QAM for extremely high throughput.
   2. Multi-Link Operation (MLO) for simultaneous multi-band usage.
   3. Wider channels up to 320 MHz.
   4. Enhanced OFDMA and MU-MIMO.
5. Key differences from Wi-Fi 5:

   1. Wi-Fi 6/6E/7 focus on efficiency, not just speed.
   2. Better handling of dense device environments.
   3. Improved latency and reliability.
   4. Advanced scheduling and resource allocation.
6. Overall, newer standards provide higher throughput, lower latency, improved capacity, and better power efficiency compared to Wi-Fi 5.

---

## 2. Explain the role of OFDMA in Wi-Fi 6 and how it improves network efficiency

1. OFDMA (Orthogonal Frequency Division Multiple Access) is a key feature introduced in Wi-Fi 6 to improve spectral efficiency.
2. It divides a channel into smaller subchannels called **Resource Units (RUs)**.
3. Multiple users can transmit or receive data simultaneously using different RUs.
4. Unlike traditional OFDM where one user occupies the entire channel, OFDMA enables parallel multi-user communication.
5. The Access Point (AP) acts as a scheduler, assigning RUs to different clients.
6. This reduces contention and waiting time among devices.
7. It is particularly beneficial for networks with many low-data-rate devices.
8. Efficiency improvements:

   1. Reduces overhead by serving multiple users in one transmission cycle.
   2. Minimizes collisions and retransmissions.
   3. Improves latency for small packets.
9. It supports both uplink and downlink transmissions.
10. In dense environments (offices, stadiums), OFDMA significantly enhances throughput.
11. It also improves power efficiency, as devices transmit only when scheduled.
12. Overall, OFDMA transforms Wi-Fi from a contention-based system to a more scheduled and efficient access mechanism.

---

## 3. Discuss the benefits of Target Wake Time (TWT) in Wi-Fi 6 for IoT devices

1. Target Wake Time (TWT) is a power-saving feature introduced in Wi-Fi 6.
2. It allows devices and the Access Point to negotiate specific wake-up times for communication.
3. Devices remain in sleep mode when not scheduled, conserving energy.
4. Benefits for IoT devices:

   1. **Extended battery life**

      * Devices wake only when necessary, reducing power consumption.
   2. **Reduced channel contention**

      * Scheduled transmissions avoid collisions.
   3. **Improved network efficiency**

      * AP coordinates multiple devices efficiently.
   4. **Lower latency for scheduled traffic**

      * Predictable communication intervals.
5. Types of TWT:

   1. Individual TWT → per-device scheduling.
   2. Broadcast TWT → group scheduling.
6. Particularly useful for:

   1. Sensors
   2. Smart home devices
   3. Wearables
7. Compared to legacy power-saving methods, TWT is more deterministic and scalable.
8. It reduces unnecessary wake-ups and idle listening.
9. Trade-offs:

   1. Requires coordination with AP.
   2. Slight complexity in scheduling.
10. Overall, TWT is critical for enabling large-scale IoT deployments with efficient power usage and reduced network congestion.

---

## 4. Explain the significance of the 6 GHz frequency band in Wi-Fi 6E

1. Wi-Fi 6E extends Wi-Fi operation into the **6 GHz band (5.925–7.125 GHz)**.
2. This band provides a large amount of additional spectrum compared to 2.4 GHz and 5 GHz.
3. Key significance:

   1. **More bandwidth availability**

      * Supports multiple wide channels (80 MHz and 160 MHz).
   2. **Reduced interference**

      * No legacy devices operating in this band.
   3. **Higher data rates**

      * Cleaner spectrum allows higher-order modulation.
4. It enables applications requiring high throughput and low latency:

   1. AR/VR
   2. 4K/8K streaming
   3. Cloud gaming
5. Improved network performance in dense environments due to less congestion.
6. Limitations:

   1. Shorter range compared to lower frequencies.
   2. Higher attenuation through walls.
7. Regulatory constraints may vary by region.
8. Devices must support Wi-Fi 6E to use this band.
9. Overall, 6 GHz is a major advancement that significantly expands Wi-Fi capacity and performance.

---

## 5. Compare and contrast Wi-Fi 6 and Wi-Fi 6E in terms of range, bandwidth, and interference

1. **Range**

   1. Wi-Fi 6 operates in 2.4 GHz and 5 GHz → better coverage.
   2. Wi-Fi 6E operates in 6 GHz → shorter range due to higher frequency.
2. **Bandwidth**

   1. Wi-Fi 6 supports limited channels in existing bands.
   2. Wi-Fi 6E offers significantly more spectrum with additional wide channels (80/160 MHz).
3. **Interference**

   1. Wi-Fi 6 faces interference from legacy devices in 2.4 and 5 GHz.
   2. Wi-Fi 6E operates in a cleaner band with minimal interference.
4. **Performance**

   1. Wi-Fi 6 improves efficiency using OFDMA and MU-MIMO.
   2. Wi-Fi 6E enhances this further with less congestion.
5. **Use cases**

   1. Wi-Fi 6 → general-purpose usage with broader coverage.
   2. Wi-Fi 6E → high-performance applications in dense environments.
6. **Device compatibility**

   1. Wi-Fi 6 works with older bands and devices.
   2. Wi-Fi 6E requires newer hardware.
7. Summary:

   1. Wi-Fi 6 provides balanced performance and coverage.
   2. Wi-Fi 6E offers higher capacity and cleaner spectrum but with reduced range.


## 6. What are the major innovations introduced in Wi-Fi 7 (802.11be)?

1. Wi-Fi 7 (802.11be), also known as Extremely High Throughput (EHT), introduces several innovations aimed at achieving multi-gigabit speeds, ultra-low latency, and improved reliability.
2. **320 MHz Channel Bandwidth**

   1. Doubles the maximum channel width compared to Wi-Fi 6 (160 MHz).
   2. Significantly increases peak data rates.
3. **4096-QAM (4K-QAM)**

   1. Encodes 12 bits per symbol.
   2. Provides ~20% higher throughput than 1024-QAM.
4. **Multi-Link Operation (MLO)**

   1. Allows simultaneous use of multiple frequency bands (2.4, 5, 6 GHz).
   2. Improves throughput and reduces latency.
5. **Enhanced OFDMA**

   1. More flexible resource unit allocation.
   2. Supports puncturing to avoid interference in parts of a channel.
6. **Multi-RU Allocation**

   1. A single user can be assigned multiple resource units.
   2. Improves efficiency and utilization.
7. **Improved MU-MIMO**

   1. Supports up to 16 spatial streams.
   2. Enhances multi-user capacity.
8. **Low Latency Features**

   1. Reduced scheduling delays.
   2. Suitable for real-time applications (AR/VR, gaming).
9. **Preamble Puncturing**

   1. Enables use of partial channels when interference exists.
   2. Improves spectrum utilization.
10. Overall, Wi-Fi 7 focuses on extremely high throughput, deterministic latency, and efficient spectrum usage, surpassing previous standards significantly.

---

## 7. Explain the concept of Multi-Link Operation (MLO) and its impact on throughput and latency

1. Multi-Link Operation (MLO) is a key feature of Wi-Fi 7 that allows a device to use multiple frequency bands simultaneously.
2. Traditionally, a Wi-Fi device connects to only one band at a time (2.4 GHz, 5 GHz, or 6 GHz).
3. MLO enables parallel transmission across multiple links, forming a single logical connection.

### Working:

4. A device establishes multiple links with the Access Point across different bands.
5. Data packets are distributed across these links dynamically.
6. Traffic scheduling ensures optimal use of each band based on conditions.

### Impact on throughput:

7. Aggregates bandwidth from multiple bands.
8. Increases overall data rate significantly.
9. Allows simultaneous transmission, improving efficiency.

### Impact on latency:

10. Reduces delay by selecting the least congested link.
11. Supports packet duplication for reliability (send same data on multiple links).
12. Minimizes retransmissions and jitter.

### Additional benefits:

13. Load balancing across bands.
14. Improved robustness in presence of interference.

### Challenges:

15. Increased complexity in scheduling and coordination.
16. Requires compatible hardware and firmware.

### Summary:

17. MLO transforms Wi-Fi from single-link to multi-link communication.
18. It plays a critical role in achieving high throughput and low latency in Wi-Fi 7 networks.

---

## 8. What is the purpose of 802.11k and v, and how does it aid in roaming?

1. IEEE 802.11k and 802.11v are amendments designed to improve network efficiency and assist clients in roaming between Access Points (APs).

### 802.11k (Radio Resource Management):

2. Provides information about neighboring APs.
3. AP sends **Neighbor Reports** containing channel, signal strength, and capabilities of nearby APs.
4. Reduces the need for full channel scanning by clients.
5. Helps clients make informed roaming decisions.

### 802.11v (Network Assisted Roaming):

6. Allows AP to guide clients in roaming decisions.
7. Uses **BSS Transition Management** frames.
8. AP suggests better APs based on load, signal quality, and policies.
9. Enables load balancing across network.

### Benefits for roaming:

10. Faster AP discovery.
11. Reduced scanning delay.
12. Improved decision-making for handoff.
13. Better distribution of clients across APs.

### Combined impact:

14. 802.11k provides information.
15. 802.11v provides guidance/control.
16. Together, they optimize roaming efficiency and reduce latency.

---

## 9. Explain the concept of Fast BSS Transition (802.11r) and its benefit in mobile environments

1. IEEE 802.11r introduces Fast BSS Transition (FT) to reduce handoff latency during roaming.
2. In traditional roaming, authentication and key exchange cause delays.
3. 802.11r optimizes this process by pre-establishing security keys.

### Working:

4. A **Pairwise Master Key (PMK)** is shared across APs within a mobility domain.
5. During roaming, client derives new session keys without full authentication.
6. Uses **FT authentication** instead of full 4-way handshake.

### Types of FT:

7. Over-the-Air (OTA) → direct communication with new AP.
8. Over-the-DS (Distribution System) → via current AP.

### Benefits:

9. Reduces handoff time from hundreds of milliseconds to a few milliseconds.
10. Ensures seamless connectivity for real-time applications.
11. Minimizes packet loss during roaming.

### Use cases:

12. VoIP calls
13. Video streaming
14. Mobile enterprise environments

### Summary:

14. 802.11r enables fast, secure transitions between APs.
15. Critical for latency-sensitive applications in mobile networks.

---

## 10. How do 802.11k/v/r work together to provide seamless roaming in enterprise networks?

1. 802.11k, 802.11v, and 802.11r complement each other to enable efficient and seamless roaming.

### Step-by-step integration:

2. **Discovery (802.11k)**

   1. Client receives neighbor reports from AP.
   2. Identifies potential target APs without full scanning.

3. **Decision Assistance (802.11v)**

   1. AP suggests optimal AP using BSS Transition Management.
   2. Considers load balancing and signal quality.

4. **Fast Transition (802.11r)**

   1. Client roams to new AP with minimal delay.
   2. Uses pre-established keys for quick authentication.

---

### Combined benefits:

5. Reduced scanning time (k).
6. Intelligent AP selection (v).
7. Fast and secure handoff (r).
8. Lower latency and minimal packet loss.

---

### Impact on enterprise networks:

9. Supports high-density deployments.
10. Enables seamless mobility for users.
11. Improves performance for real-time applications.

---


