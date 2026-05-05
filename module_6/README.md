

# Module 6 – Assignment Questions

## 1. What are the pillars of Wi-Fi security?

1. Wi-Fi security is built on a set of fundamental pillars that ensure safe and reliable communication over a shared wireless medium.
2. The first pillar is **confidentiality**, which ensures that transmitted data is protected from unauthorized access. Encryption mechanisms such as AES are used to convert plain data into unreadable form so that only intended receivers can interpret it.
3. The second pillar is **integrity**, which ensures that data is not altered during transmission. Message Integrity Codes (MIC) and cryptographic hashing techniques are used to detect any tampering or corruption.
4. The third pillar is **authentication**, which verifies the identity of devices attempting to connect to the network. Mechanisms such as pre-shared keys (PSK) or enterprise authentication (802.1X with EAP) ensure that only authorized users gain access.
5. The fourth pillar is **authorization**, which determines what an authenticated user is allowed to do within the network. This may include access control policies, VLAN assignments, or role-based permissions.
6. The fifth pillar is **non-repudiation**, ensuring that actions performed on the network can be traced back to a specific user or device. This is important in enterprise environments for accountability.
7. The sixth pillar is **availability**, which ensures that network resources are accessible when needed. Protection against denial-of-service attacks and interference plays a role here.
8. These pillars work together to provide a comprehensive security framework. Without any one of them, the network becomes vulnerable to attacks such as eavesdropping, spoofing, or data manipulation.

---

## 2. Explain the difference between authentication and encryption in WiFi security

1. Authentication and encryption are two distinct but complementary aspects of Wi-Fi security.
2. **Authentication** is the process of verifying the identity of a device or user attempting to connect to a wireless network. It ensures that only legitimate users are allowed access.
3. Authentication can be implemented using methods such as open authentication, pre-shared key (PSK), or enterprise authentication using 802.1X and EAP.
4. It occurs before a device is granted access to the network and is typically part of the connection establishment process.
5. **Encryption**, on the other hand, is the process of protecting the data being transmitted over the network. It ensures that even if data is intercepted, it cannot be understood without the correct decryption key.
6. Encryption algorithms such as TKIP (used in WPA) and AES-CCMP (used in WPA2 and WPA3) are applied to data frames.
7. Authentication answers the question “who are you?”, while encryption answers “how is your data protected?”.
8. Authentication prevents unauthorized access, whereas encryption prevents unauthorized reading of data.
9. Both are essential; authentication without encryption leaves data exposed, and encryption without authentication allows unauthorized users to join the network.
10. In modern Wi-Fi security, both processes are tightly integrated to ensure secure access and communication.

---

## 3. Explain the differences between WEP, WPA, WPA2, and WPA3

1. **WEP (Wired Equivalent Privacy)** is the earliest Wi-Fi security protocol. It uses RC4 stream cipher and a static key. It provides basic encryption but lacks strong integrity and key management mechanisms.
2. **WPA (Wi-Fi Protected Access)** was introduced as an improvement over WEP. It uses TKIP (Temporal Key Integrity Protocol), which dynamically changes keys and adds better integrity checks. However, it still relies on RC4 and has known vulnerabilities.
3. **WPA2** replaces TKIP with AES-based CCMP encryption, providing strong confidentiality and integrity. It supports both personal (PSK) and enterprise (802.1X) modes. WPA2 became the standard for secure Wi-Fi for many years.
4. **WPA3** is the latest security protocol, designed to address weaknesses in WPA2. It introduces SAE (Simultaneous Authentication of Equals), which replaces PSK and provides protection against offline dictionary attacks.
5. WPA3 also improves encryption strength and includes forward secrecy, meaning past sessions remain secure even if keys are compromised later.
6. WPA3 introduces enhanced protection for open networks (OWE) and stronger enterprise security (192-bit mode).
7. Key differences:

   1. WEP → weak encryption, static keys.
   2. WPA → improved but still vulnerable.
   3. WPA2 → strong encryption, widely adopted.
   4. WPA3 → advanced security, resistant to modern attacks.
8. The evolution reflects increasing security requirements and advancements in cryptographic techniques.

---

## 4. Why is WEP considered insecure compared to WPA2 or WPA3?

1. WEP is considered insecure due to fundamental flaws in its design and implementation.
2. It uses the RC4 stream cipher with a small initialization vector (IV), typically 24 bits, which leads to frequent reuse of keys.
3. Reuse of IVs allows attackers to analyze traffic and recover encryption keys through statistical attacks.
4. WEP uses static keys that do not change dynamically, making it easier for attackers to crack the network once enough packets are captured.
5. The integrity mechanism in WEP relies on a weak CRC-32 checksum, which is not cryptographically secure and can be easily manipulated.
6. WEP does not provide proper authentication mechanisms, making it vulnerable to spoofing attacks.
7. Tools and techniques exist that can break WEP encryption within minutes using readily available hardware and software.
8. In contrast, WPA2 uses AES-CCMP, which provides strong encryption and integrity protection.
9. WPA3 further enhances security with SAE and forward secrecy, making attacks significantly more difficult.
10. WEP lacks protection against modern attack vectors such as replay attacks and dictionary attacks.
11. Due to these weaknesses, WEP has been deprecated and is no longer recommended for any secure network.

---

## 5. Why was WPA2 introduced?

1. WPA2 was introduced to address the security limitations present in WEP and WPA.
2. WPA, although an improvement over WEP, still relied on RC4 and TKIP, which were not considered strong enough for long-term security.
3. WPA2 replaced these mechanisms with **AES-based CCMP**, a robust encryption standard approved for secure communications.
4. The introduction of WPA2 ensured stronger data confidentiality and integrity compared to earlier protocols.
5. It supports both personal (PSK) and enterprise (802.1X with EAP) authentication methods, making it suitable for both home and corporate environments.
6. WPA2 also introduced improved key management and secure key exchange processes through the 4-way handshake.
7. It provides protection against packet tampering, replay attacks, and unauthorized access.
8. WPA2 became mandatory for Wi-Fi certification, ensuring widespread adoption and interoperability among devices.
9. It was designed to meet the growing need for secure wireless communication as Wi-Fi usage expanded globally.
10. Despite its strengths, WPA2 later faced vulnerabilities such as KRACK attacks, which led to the development of WPA3.
11. Overall, WPA2 marked a significant step forward in Wi-Fi security by providing a strong and standardized encryption framework.

## 6. What is the role of the Pairwise Master Key (PMK) in the 4-way handshake?

1. The Pairwise Master Key (PMK) is the foundational key used to derive all session-specific encryption keys during the 4-way handshake.
2. It is not directly used for encrypting data frames; instead, it acts as a root secret from which other keys are generated.
3. In a personal network (WPA2/WPA3-PSK), the PMK is derived from the passphrase and SSID using a key derivation function (PBKDF2).
4. In enterprise networks (802.1X/EAP), the PMK is generated as a result of successful authentication with an authentication server.
5. During the 4-way handshake, both the client (STA) and access point (AP) already possess the PMK before the exchange begins.
6. The PMK is combined with other parameters such as ANonce (from AP), SNonce (from STA), and MAC addresses of both devices.
7. Using these inputs, both sides independently derive the Pairwise Transient Key (PTK).
8. The PTK is further divided into subkeys used for encryption, integrity protection, and key exchange.
9. The PMK ensures that both parties derive identical PTKs without transmitting the PMK over the air.
10. This approach enhances security by preventing exposure of the root key.
11. If the PMK differs between client and AP, the derived PTKs will not match, leading to handshake failure.
12. Thus, the PMK plays a central role in securely establishing session keys and enabling encrypted communication.

---

## 7. How does the 4-way handshake ensure mutual authentication between the client and the access point?

1. The 4-way handshake ensures mutual authentication by verifying that both the client and the AP possess the same PMK.
2. It uses a challenge-response mechanism involving random nonces and cryptographic checks.
3. In Message 1, the AP sends a random value called ANonce to the client.
4. In Message 2, the client generates SNonce and computes the PTK using PMK, ANonce, SNonce, and MAC addresses.
5. The client sends SNonce along with a Message Integrity Code (MIC), which is calculated using part of the PTK.
6. The AP independently computes the PTK using the same inputs and verifies the MIC.
7. Successful MIC verification confirms that the client has the correct PMK.
8. In Message 3, the AP sends the Group Temporal Key (GTK) along with its own MIC.
9. The client verifies this MIC using its computed PTK.
10. This step confirms that the AP also possesses the correct PMK.
11. Message 4 is an acknowledgment from the client confirming successful key installation.
12. Through this exchange, both sides validate each other without directly sharing the PMK.
13. The use of nonces prevents replay attacks, and MIC ensures message integrity.
14. This process establishes trust and enables secure communication.

---

## 8. What will happen if we put a wrong passphrase during a 4-way handshake?

1. When a wrong passphrase is entered, the client derives an incorrect PMK.
2. Since the AP has the correct PMK, both sides will compute different PTKs during the handshake.
3. In Message 2, the client sends SNonce and MIC computed using its incorrect PTK.
4. The AP attempts to verify the MIC using its own PTK (derived from correct PMK).
5. The MIC verification fails because the keys do not match.
6. As a result, the AP does not proceed with the handshake and may discard the message.
7. In some cases, the AP may send a deauthentication or disassociation frame to the client.
8. The client may retry the handshake multiple times, but it will continue to fail.
9. Eventually, the connection attempt is rejected, and the client remains disconnected.
10. No encryption keys (PTK or GTK) are successfully installed.
11. This mechanism ensures that only users with the correct passphrase can establish a secure session.
12. It also prevents unauthorized access without exposing the actual passphrase.
13. From the user perspective, this appears as a “wrong password” or “authentication failed” error.
14. Thus, incorrect passphrases lead to handshake failure and denied network access.

---

## 9. What problem does 802.1X solve in a network?

1. 802.1X is designed to solve the problem of **unauthorized network access** in both wired and wireless environments.
2. In traditional networks using shared passwords (PSK), all users share the same credentials, which creates security risks.
3. If one user is compromised, the entire network becomes vulnerable.
4. 802.1X introduces **port-based network access control**, where each device must authenticate individually before gaining access.
5. It separates authentication from encryption by using an external authentication server (typically RADIUS).
6. The key components are:

   1. Supplicant (client device)
   2. Authenticator (AP or switch)
   3. Authentication server
7. The client must prove its identity using credentials such as username/password, certificates, or tokens.
8. Only after successful authentication is network access granted.
9. It enables dynamic key generation instead of static shared keys.
10. It supports centralized user management and policy enforcement.
11. It also allows for role-based access, VLAN assignment, and accounting.
12. 802.1X eliminates the need for shared secrets and improves scalability.
13. It is widely used in enterprise networks for secure and controlled access.

---

## 10. How does 802.1X enhance security over wireless networks?

1. 802.1X enhances wireless security by providing strong, centralized authentication and dynamic key management.
2. Unlike PSK-based systems, each user has unique credentials, reducing the risk of unauthorized access.
3. Authentication is performed using EAP (Extensible Authentication Protocol), which supports multiple secure methods such as EAP-TLS.
4. Credentials are verified by a centralized authentication server, ensuring consistent security policies.
5. After successful authentication, a unique PMK is generated for each session.
6. This PMK is used in the 4-way handshake to derive session-specific encryption keys.
7. It eliminates the use of static shared keys, reducing the risk of key compromise.
8. 802.1X supports mutual authentication between client and server, preventing rogue access points.
9. It enables dynamic key rotation and reauthentication, improving long-term security.
10. Additional features include VLAN assignment, access control, and user-specific policies.
11. It integrates well with enterprise security systems such as directory services.
12. By providing per-user authentication, strong encryption, and centralized control, 802.1X significantly improves the overall security posture of wireless networks.
