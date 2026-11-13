# Experiment 7: Analyze WPA2 Wireless Security and Capture Handshake with Wireshark

## 1. Aim
To capture and analyze the WPA2 4-way handshake using Wireshark to understand secure wireless communication.

## 2. Requirements
- Computer with Wireshark installed
- Wi-Fi network secured with WPA2
- Wireless network adapter supporting monitor mode
- Network connection

## 3. Methodology

### A. Open Wireshark

Open Wireshark and select the wireless network interface. Enable monitor mode if supported by the adapter and operating system.

### B. Start Packet Capture

Start capturing wireless packets using the selected interface.

### C. Connect to Wi-Fi

Connect a device to the WPA2-protected wireless network to generate authentication traffic.

### D. Capture the Handshake

Capture the WPA2 4-way handshake during the device connection process.

### E. Apply Display Filter

Enter the following filter in Wireshark:

```text
eapol
```

Observe the four EAPOL handshake messages.

## 4. Context

WPA2 (Wi-Fi Protected Access 2) is a wireless security protocol used to protect Wi-Fi networks from unauthorized access. It uses encryption to secure communication between wireless devices and access points.

## 5. Theory

WPA2 uses a 4-way handshake to establish encryption keys between a client and an access point.

- **Message 1:** Access Point sends a random number called ANonce.
- **Message 2:** Client sends its random number called SNonce.
- **Message 3:** Access Point sends key installation information.
- **Message 4:** Client confirms the key installation.

The handshake helps both devices establish a secure connection.

## 6. Visualization

```text
Wireless Client                 Access Point
      |                               |
      | <------ Message 1 ------------|
      | ------ Message 2 ------------>|
      | <------ Message 3 ------------|
      | ------ Message 4 ------------>|
      |                               |
      | <== Secure Communication ===> |
```

## 7. Results

The WPA2 4-way handshake was captured and analyzed using Wireshark, and the four EAPOL messages were studied.

## 8. Discussion

The WPA2 handshake establishes secure communication between a wireless client and an access point. Wireshark helps analyze network packets and understand the authentication process.

## 9. Improvement

Use strong Wi-Fi passwords, enable WPA2-AES or WPA3 security, update router firmware, and avoid sharing Wi-Fi credentials with unauthorized users.
