
# Module 3 – Assignment

# 1. What are the different 802.11 PHY layer standards? Compare their characteristics.
## 1. IEEE 802.11 PHY Layer Standards and Comparison

## 1. IEEE 802.11 (Legacy – 1997)

1. First WLAN standard.
2. Data rates: 1–2 Mbps.
3. Frequency band: 2.4 GHz.
4. Modulation: FHSS and DSSS.
5. Very limited throughput and mostly obsolete.

## 2. IEEE 802.11a

1. Operates in 5 GHz band.
2. Data rates: up to 54 Mbps.
3. Modulation: OFDM.
4. 20 MHz channel bandwidth.
5. Shorter range compared to 2.4 GHz due to higher frequency.
6. Less interference (no Bluetooth/microwave overlap).

## 3. IEEE 802.11b

1. Operates in 2.4 GHz band.
2. Data rates: up to 11 Mbps.
3. Modulation: DSSS (CCK).
4. Better range than 802.11a.
5. High interference due to crowded 2.4 GHz band.

## 4. IEEE 802.11g

1. Operates in 2.4 GHz band.
2. Data rates: up to 54 Mbps.
3. Modulation: OFDM (backward compatible with 802.11b DSSS).
4. Same range as 802.11b.
5. Higher interference susceptibility than 5 GHz systems.

## 5. IEEE 802.11n (Wi-Fi 4)

1. Operates in 2.4 GHz and 5 GHz bands.
2. Data rates: up to 600 Mbps.
3. Modulation: OFDM with MIMO support.
4. Channel bandwidth: 20/40 MHz.
5. Uses spatial multiplexing (multiple antennas).
6. Significant improvement in range and throughput.

## 6. IEEE 802.11ac (Wi-Fi 5)

1. Operates only in 5 GHz band.
2. Data rates: up to several Gbps (theoretical ~6.9 Gbps).
3. Modulation: OFDM with MU-MIMO.
4. Channel bandwidth: 20/40/80/160 MHz.
5. Higher-order modulation: up to 256-QAM.
6. Designed for high throughput and dense environments.

## 7. IEEE 802.11ax (Wi-Fi 6 / Wi-Fi 6E)

1. Operates in 2.4 GHz, 5 GHz, and 6 GHz (6E).
2. Data rates: up to ~9.6 Gbps.
3. Modulation: OFDMA + MU-MIMO.
4. Higher efficiency in dense networks.
5. Uses BSS coloring to reduce interference.
6. Supports 1024-QAM.
7. Improved power efficiency (TWT – Target Wake Time).

## 8. IEEE 802.11be (Wi-Fi 7 – emerging)

1. Operates in 2.4 GHz, 5 GHz, and 6 GHz.
2. Data rates: expected up to 30–46 Gbps.
3. Modulation: OFDMA + enhanced MU-MIMO.
4. Channel bandwidth: up to 320 MHz.
5. Supports 4096-QAM.
6. Multi-Link Operation (MLO) for parallel transmissions.
7. Designed for ultra-low latency applications (AR/VR, gaming).

## Summary Comparison Points

1. Frequency evolution: 2.4 GHz → 5 GHz → 6 GHz.
2. Modulation improvement: DSSS/FHSS → OFDM → MU-MIMO + OFDMA.
3. Throughput increase: Mbps → multi-Gbps.
4. Efficiency improvements for dense environments in newer standards.
5. Antenna techniques evolved from none → MIMO → massive MIMO + MLO.



# 2. What are DSSS and FHSS? How do they work? 

# 2. DSSS and FHSS: Definition and Working

## 1. Direct Sequence Spread Spectrum (DSSS)

### 1. Definition

1. DSSS is a spread spectrum technique used in early IEEE 802.11 standards.
2. It spreads the signal over a wider bandwidth than required using a pseudo-noise (PN) code.

### 2. Working Principle

1. Original data bits are multiplied by a high-rate pseudo-random binary sequence called a chip sequence.
2. Each data bit is converted into multiple chips (spreading process).
3. The resulting wideband signal is transmitted over the channel.
4. At the receiver, the same PN code is used to correlate and reconstruct the original data.

### 3. Key Characteristics

1. Uses full bandwidth simultaneously.
2. Provides resistance to interference and noise.
3. Allows multiple users with different codes in some systems.
4. Common in IEEE 802.11b (early Wi-Fi).

---

## 2. Frequency Hopping Spread Spectrum (FHSS)

### 1. Definition

1. FHSS is a technique where the carrier frequency changes (hops) rapidly according to a predefined sequence.
2. Each transmission uses a narrowband signal but changes frequency over time.

### 2. Working Principle

1. The available frequency band is divided into multiple small channels.
2. Transmitter and receiver follow a synchronized hopping pattern.
3. Data is transmitted on one frequency channel for a short time (dwell time).
4. Then both hop to another frequency channel and continue transmission.
5. Receiver must follow the same hopping sequence to decode data correctly.

### 3. Key Characteristics

1. Reduces interference by avoiding crowded frequencies.
2. More secure due to unpredictable hopping pattern.
3. Lower data rates compared to DSSS in Wi-Fi systems.
4. Used in early IEEE 802.11 and Bluetooth (classic).

---

## 3. DSSS vs FHSS Comparison

1. Spectrum usage:

   * DSSS: Spreads signal across wide band simultaneously.
   * FHSS: Uses narrow band but switches frequencies over time.

2. Interference handling:

   * DSSS: Robust due to spreading gain.
   * FHSS: Avoids interference by hopping away.

3. Complexity:

   * DSSS: Requires correlation with PN code.
   * FHSS: Requires precise frequency synchronization.

4. Throughput:

   * DSSS: Higher than FHSS in early Wi-Fi.
   * FHSS: Generally lower throughput.

5. Usage in Wi-Fi:

   * DSSS: Used in 802.11b.
   * FHSS: Rare in modern Wi-Fi, mostly legacy systems.


# 3. How do modulation schemes work in the PHY layer? Compare different modulation schemes and their performance across various Wi-Fi standards.

## 3. How modulation schemes work in the PHY layer and their comparison across Wi-Fi standards

### 1. Role of modulation in the PHY layer

1. Modulation maps digital bits (0s and 1s) into analog waveforms suitable for transmission over the wireless medium.
2. It alters properties of a carrier signal such as amplitude, phase, or frequency to encode information.
3. The receiver demodulates the signal to recover the original bitstream.
4. In Wi-Fi, modulation works together with coding schemes (FEC) and channel bandwidth to determine data rate and reliability.

---

### 2. Basic working principle

1. Input binary data is grouped into symbols (e.g., 1, 2, 4, 6, 8, or 10 bits per symbol).
2. Each symbol is mapped to a unique signal state (constellation point).
3. The modulated signal is transmitted over RF channels.
4. At the receiver, signal distortions (noise, fading) affect symbol detection.
5. Higher-order modulation increases data rate but is more sensitive to noise.

---

### 3. Common modulation schemes in Wi-Fi

1. **BPSK (Binary Phase Shift Keying)**

   * 1 bit per symbol
   * Two phase states (0°, 180°)
   * Very robust, lowest data rate

2. **QPSK (Quadrature Phase Shift Keying)**

   * 2 bits per symbol
   * Four phase states
   * Moderate robustness and data rate

3. **16-QAM (Quadrature Amplitude Modulation)**

   * 4 bits per symbol
   * Combines amplitude and phase variations
   * Higher data rate, moderate noise sensitivity

4. **64-QAM**

   * 6 bits per symbol
   * High data rate, requires good SNR

5. **256-QAM**

   * 8 bits per symbol
   * Very high throughput, sensitive to noise

6. **1024-QAM**

   * 10 bits per symbol
   * Used in newer standards, requires excellent channel conditions

---

### 4. Performance comparison of modulation schemes

| Modulation | Bits/Symbol | Data Rate      | Noise Immunity | SNR Requirement |
| ---------- | ----------- | -------------- | -------------- | --------------- |
| BPSK       | 1           | Very Low       | Very High      | Very Low        |
| QPSK       | 2           | Low            | High           | Low             |
| 16-QAM     | 4           | Medium         | Moderate       | Medium          |
| 64-QAM     | 6           | High           | Low            | High            |
| 256-QAM    | 8           | Very High      | Very Low       | Very High       |
| 1024-QAM   | 10          | Extremely High | Extremely Low  | Extremely High  |

---

### 5. Modulation usage across Wi-Fi standards

1. **802.11b (DSSS)**

   * Uses DBPSK, DQPSK, and CCK
   * Low data rates (up to 11 Mbps)
   * High robustness

2. **802.11a/g (OFDM-based)**

   * Uses BPSK, QPSK, 16-QAM, 64-QAM
   * Data rates up to 54 Mbps
   * Adaptive modulation based on channel conditions

3. **802.11n (Wi-Fi 4)**

   * Uses up to 64-QAM
   * Introduces MIMO for higher throughput
   * Data rates up to 600 Mbps

4. **802.11ac (Wi-Fi 5)**

   * Introduces 256-QAM
   * Wider channels (80/160 MHz)
   * Higher throughput (Gbps range)

5. **802.11ax (Wi-Fi 6 / 6E)**

   * Uses up to 1024-QAM
   * OFDMA for multi-user efficiency
   * Better performance in dense environments

6. **802.11be (Wi-Fi 7)**

   * Introduces 4096-QAM (12 bits per symbol)
   * Extremely high throughput (multi-Gbps)
   * Requires very high SNR and ideal conditions

---

### 6. Key observations

1. Higher-order modulation increases spectral efficiency (bits/sec/Hz).
2. Trade-off exists between data rate and robustness.
3. Wi-Fi uses adaptive modulation and coding (AMC) to dynamically adjust modulation based on channel quality.
4. Modern standards combine high-order modulation with MIMO and wider bandwidths for maximum throughput.


# 4. What is the significance of OFDM in WLAN? How does it improve performance? 

## 4. Significance of OFDM in WLAN and how it improves performance

### 1. Role of OFDM in WLAN

1. OFDM (Orthogonal Frequency Division Multiplexing) is the core transmission technique used in modern WLAN standards such as 802.11a/g/n/ac/ax/be.
2. It enables high-speed data transmission over wireless channels that suffer from multipath propagation and interference.
3. It replaces older single-carrier techniques (like DSSS) for better efficiency and reliability.

---

### 2. Key significance of OFDM

1. **Efficient spectrum utilization**

   * Subcarriers overlap but remain orthogonal, maximizing bandwidth usage.

2. **Parallel data transmission**

   * Splits high-rate data into multiple low-rate streams transmitted simultaneously.

3. **Foundation for high data rates**

   * Supports higher-order modulation (e.g., 64-QAM, 256-QAM, 1024-QAM).

4. **Compatibility with advanced techniques**

   * Works with MIMO and OFDMA for enhanced performance in modern Wi-Fi.

---

### 3. How OFDM improves performance

#### 3.1 Resistance to multipath fading

1. Wireless signals reflect off obstacles, causing delayed copies (multipath).
2. OFDM uses long symbol duration and cyclic prefix to reduce inter-symbol interference (ISI).
3. This improves signal reliability in indoor and dense environments.

---

#### 3.2 Reduced inter-symbol interference (ISI)

1. By transmitting data at lower rates on each subcarrier, symbol duration increases.
2. Longer symbols reduce overlap between consecutive symbols.
3. Cyclic prefix further mitigates ISI.

---

#### 3.3 Adaptive modulation and coding

1. Each subcarrier can use different modulation schemes based on channel conditions.
2. Good channels use higher-order QAM for higher throughput.
3. Poor channels fall back to robust schemes like BPSK/QPSK.

---

#### 3.4 High data throughput

1. Parallel transmission across subcarriers increases total data rate.
2. Combined with wide channels (20/40/80/160 MHz), achieves Mbps to multi-Gbps speeds.

---

#### 3.5 Robustness to frequency-selective fading

1. In wideband channels, some frequencies may fade more than others.
2. OFDM spreads data across many subcarriers.
3. Only a few subcarriers are affected, not the entire transmission.

---

#### 3.6 Simplified equalization

1. Each subcarrier experiences flat fading instead of complex frequency-selective fading.
2. This reduces receiver complexity compared to single-carrier systems.

---

### 4. Additional benefits in modern WLAN (802.11ax and beyond)

1. **OFDMA (Orthogonal Frequency Division Multiple Access)**

   * Allows multiple users to share subcarriers simultaneously.

2. **Better performance in dense networks**

   * Efficient resource allocation reduces congestion and latency.

3. **Improved power efficiency**

   * Devices can transmit smaller chunks of data more efficiently.

---

### 5. Key observations

1. OFDM significantly improves reliability and throughput in wireless environments.
2. It is essential for handling multipath and interference in indoor WLAN scenarios.
3. Modern Wi-Fi performance gains are largely built on OFDM combined with MIMO and higher-order modulation.


# 5. How are frequency bands divided for Wi-Fi? Explain different bands and their channels.

1. Wi-Fi operates mainly in three frequency bands: **2.4 GHz, 5 GHz, and 6 GHz**. Each band is divided into smaller units called channels.
2. **2.4 GHz band (2.4–2.4835 GHz)**

   1. Divided into 14 channels (depending on region).
   2. Each channel is 20 MHz wide but overlaps with adjacent channels.
   3. Non-overlapping channels: 1, 6, and 11.
   4. Offers wider coverage but suffers from interference (Bluetooth, microwaves).
3. **5 GHz band (5.15–5.825 GHz)**

   1. Provides many non-overlapping channels.
   2. Supports wider bandwidths: 20, 40, 80, and 160 MHz.
   3. Less interference and higher data rates than 2.4 GHz.
   4. Includes DFS channels (require radar detection).
4. **6 GHz band (5.925–7.125 GHz, Wi-Fi 6E/7)**

   1. Offers large contiguous spectrum.
   2. Supports multiple 80 MHz and 160 MHz channels without overlap.
   3. Ideal for high-throughput and low-latency applications.
5. Channel bonding combines adjacent channels to increase bandwidth and throughput.
6. Trade-offs:

   1. Lower frequency → better range, lower speed.
   2. Higher frequency → higher speed, shorter range.

---

# 6. What is the role of Guard Intervals in WLAN transmission? How does a short Guard Interval improve efficiency?

1. A Guard Interval (GI) is a time gap inserted between consecutive OFDM symbols.
2. It prevents **inter-symbol interference (ISI)** caused by multipath propagation.
3. Implemented as a **cyclic prefix**, which repeats the end portion of the symbol at the beginning.
4. Typical GI values:

   1. Long GI: 800 ns
   2. Short GI: 400 ns (802.11n/ac) or even smaller in newer standards
5. Role of GI:

   1. Absorbs delayed signal reflections.
   2. Maintains orthogonality between subcarriers.
   3. Ensures reliable symbol detection.
6. **Short Guard Interval (SGI)**:

   1. Reduces overhead time between symbols.
   2. Increases symbol rate → higher data throughput (~10–11% gain).
   3. Works well in environments with minimal multipath delay.
7. Trade-offs:

   1. SGI improves efficiency but is more sensitive to delay spread.
   2. Long GI is more robust in harsh environments.
8. Adaptive systems switch between GI values based on channel conditions.

---

# 7. Describe the structure of an 802.11 PHY layer frame. What are its key components?

1. The PHY frame in Wi-Fi is called a **PPDU (PLCP Protocol Data Unit)**.
2. It consists of two major parts: **Preamble/Header** and **Payload**.
3. **Preamble**

   1. Used for synchronization and channel estimation.
   2. Helps receiver detect the start of the frame.
   3. Includes training fields (short and long training sequences).
4. **PHY Header (PLCP Header)**

   1. Contains transmission parameters such as:

      * Data rate
      * Modulation and coding scheme (MCS)
      * Frame length
   2. Enables receiver to correctly decode payload.
5. **Data field (PSDU)**

   1. Carries MAC layer frame.
   2. Includes user data and higher-layer information.
6. **Optional fields** (in advanced standards):

   1. Signal extension
   2. Pilot tones for channel tracking
7. Key characteristics:

   1. Highly structured for reliable reception.
   2. Uses OFDM symbols for transmission.
   3. Includes error correction coding.

---

# 8. What is the difference between OFDM and OFDMA?

1. **OFDM (Orthogonal Frequency Division Multiplexing)**

   1. Divides channel into multiple subcarriers.
   2. All subcarriers are assigned to a single user at a time.
   3. Used in earlier Wi-Fi standards (802.11a/g/n/ac).
2. **OFDMA (Orthogonal Frequency Division Multiple Access)**

   1. Extends OFDM by dividing subcarriers into groups called Resource Units (RUs).
   2. Multiple users can transmit simultaneously using different RUs.
   3. Introduced in 802.11ax (Wi-Fi 6).
3. Key differences:

   1. OFDM → single-user transmission per time slot.
   2. OFDMA → multi-user transmission in parallel.
4. Performance comparison:

   1. OFDM is efficient for high data rates but inefficient for small packets.
   2. OFDMA improves spectral efficiency and reduces latency.
5. Benefits of OFDMA:

   1. Better performance in dense networks.
   2. Reduced contention and overhead.
   3. Improved power efficiency for devices.

---

# 9. What is the difference between MIMO and MU-MIMO?

1. **MIMO (Multiple Input Multiple Output)**

   1. Uses multiple antennas at transmitter and receiver.
   2. Improves data rate and reliability via spatial multiplexing and diversity.
   3. Typically serves a single user (SU-MIMO).
2. **MU-MIMO (Multi-User MIMO)**

   1. Extends MIMO to serve multiple users simultaneously.
   2. Different spatial streams are allocated to different users.
3. Key differences:

   1. MIMO → multiple streams for one user.
   2. MU-MIMO → multiple users served at once.
4. Advantages of MIMO:

   1. Increased throughput for individual devices.
   2. Better signal robustness.
5. Advantages of MU-MIMO:

   1. Improves network capacity.
   2. Reduces waiting time for users.
6. Usage:

   1. MIMO introduced in 802.11n.
   2. MU-MIMO enhanced in 802.11ac and 802.11ax.

---

# 10. What are PPDU, PLCP, and PMD in the PHY layer?

1. **PPDU (PLCP Protocol Data Unit)**

   1. The complete PHY-layer frame transmitted over the air.
   2. Contains preamble, header, and payload.
2. **PLCP (Physical Layer Convergence Procedure)**

   1. Acts as an interface between MAC and PHY.
   2. Converts MAC frames (MPDU) into PPDU format.
   3. Adds headers and manages framing.
3. **PMD (Physical Medium Dependent)**

   1. Handles actual signal transmission over medium.
   2. Performs modulation, coding, and RF transmission.
4. Relationship:

   1. MAC → PLCP → PMD → transmission over air.
5. Summary:

   1. PLCP prepares data.
   2. PMD transmits data.
   3. PPDU is the final transmitted unit.


---

# 11. What are the types of PPDU? Explain the PPDU frame format across different Wi-Fi generations.

1. PPDU formats vary across Wi-Fi standards.
2. **Legacy PPDU (802.11a/g)**

   1. Fields: Preamble + Signal + Data
   2. Simple structure for basic OFDM transmission.
3. **HT PPDU (802.11n)**

   1. Adds High Throughput fields (HT-SIG).
   2. Supports MIMO and higher data rates.
4. **VHT PPDU (802.11ac)**

   1. Includes VHT-SIG-A and VHT-SIG-B fields.
   2. Supports 256-QAM and wider channels.
5. **HE PPDU (802.11ax)**

   1. Adds HE-SIG fields and resource unit allocation info.
   2. Supports OFDMA and MU-MIMO.
6. **EHT PPDU (802.11be)**

   1. Designed for extremely high throughput.
   2. Includes advanced signaling for 4096-QAM and multi-link operation.
7. Common components across all formats:

   1. Preamble (training fields)
   2. Signal/header fields
   3. Data payload
8. Evolution trend:

   1. Increasing complexity to support higher throughput and multi-user features.

---

# 12. How is the data rate calculated?

1. Wi-Fi data rate depends on several PHY parameters.
2. General formula:

\text{Data Rate} = \frac{N_{ss} \times N_{bpsc} \times N_{sd} \times R}{T_{sym}}

3. Where:

   1. (N_{ss}): Number of spatial streams
   2. (N_{bpsc}): Bits per subcarrier (depends on modulation)
   3. (N_{sd}): Number of data subcarriers
   4. (R): Coding rate
   5. (T_{sym}): OFDM symbol duration (including GI)

4. Factors affecting data rate:

   1. **Modulation scheme** (e.g., BPSK to 1024-QAM)
   2. **Channel bandwidth** (20–160 MHz)
   3. **Number of spatial streams (MIMO)**
   4. **Guard interval duration**

5. Example insights:

   1. Higher QAM → more bits per symbol → higher rate.
   2. Wider channels → more subcarriers → higher rate.
   3. Shorter GI → more symbols per second.

6. Data rates range from a few Mbps (legacy) to multi-Gbps (Wi-Fi 6/7).

