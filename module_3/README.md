
# Module 3 – Assignment

# 1. What are the different 802.11 PHY layer standards? Compare their characteristics.
# 1. IEEE 802.11 PHY Layer Standards and Comparison

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
# 4. What is the significance of OFDM in WLAN? How does it improve performance?
# 5. How are frequency bands divided for Wi-Fi? Explain different bands and their channels.
# 6. What is the role of Guard Intervals in WLAN transmission? How does a short Guard Interval improve efficiency?
# 7. Describe the structure of an 802.11 PHY layer frame. What are its key components?
# 8. What is the difference between OFDM and OFDMA?
# 9. What is the difference between MIMO and MU-MIMO?
# 10. What are PPDU, PLCP, and PMD in the PHY layer?
# 11. What are the types of PPDU? Explain the PPDU frame format across different Wi-Fi generations.
# 12. How is the data rate calculated?
