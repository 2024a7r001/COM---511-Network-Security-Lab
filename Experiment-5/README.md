# Experiment 5: Capture and Analyze TLS Handshake Using Wireshark

## 1. Aim
To capture and analyze the TLS handshake process during HTTPS communication using Wireshark.

## 2. Requirements
- Wireshark
- Computer with an internet connection
- Web browser

## 3. Methodology
1. Open Wireshark and select the active Wi-Fi or Ethernet interface.
2. Start capturing network packets.
3. Open an HTTPS website in a web browser.
4. Stop the capture after the website loads.
5. Apply the display filter `tls.handshake`.
6. Select the Client Hello and Server Hello packets.
7. Expand Transport Layer Security (TLS) in the packet details pane.

## 4. Context
TLS (Transport Layer Security) provides secure communication between a client and a server. HTTPS uses TLS to protect web traffic.

## 5. Theory
The TLS handshake establishes security settings and encryption keys for communication.

- **Client Hello:** The client sends supported TLS versions and cryptographic options.
- **Server Hello:** The server selects the TLS version and security parameters.
- **Certificate:** The server provides a digital certificate to authenticate its identity.
- **Key Establishment:** The client and server establish shared session keys.
- **Finished:** Both sides verify the handshake before exchanging protected application data.

TLS provides confidentiality, integrity, and server authentication.

## 6. Visualization

```text
Client                         Server
   | -------- Client Hello ------> |
   | <------- Server Hello ------- |
   | <--- Certificate / Keys ----> |
   | <-------- Finished ---------> |
   | <==== Encrypted HTTPS ======> |
```

## 7. Results
TLS handshake packets were captured and analyzed successfully using Wireshark. Client Hello and Server Hello messages were identified.

## 8. Discussion
Wireshark helps inspect TLS handshake messages and understand how secure communication is established. In TLS 1.3, some handshake information is encrypted and may not be visible without decryption.

## 9. Improvement
Use updated TLS versions, valid digital certificates, and strong cryptographic algorithms. Avoid outdated protocols and weak cipher suites.
