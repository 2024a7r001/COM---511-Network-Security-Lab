# Experiment 6: Establish Secure Remote Login Using SSH

## 1. Aim
To demonstrate secure remote server access using SSH with password-based and key-based authentication.

## 2. Requirements
- Computer with an SSH client
- Remote server with an SSH server enabled
- Network connection

## 3. Methodology

### A. Check SSH availability

Open PowerShell or a Linux terminal and run:

```bash
ssh -V
```

### B. Password-Based Authentication

Connect to the remote server:

```bash
ssh username@server_ip
```

Replace `username` with the remote account name and `server_ip` with the server's IP address. Enter the password when prompted.

### C. Key-Based Authentication

Generate an SSH key pair:

```bash
ssh-keygen -t ed25519
```

Install the public key on the remote server. Keep the private key secret.

Connect using the private key:

```bash
ssh -i ~/.ssh/id_ed25519 username@server_ip
```

## 4. Context
SSH (Secure Shell) is a network protocol used to access and manage remote computers securely. It encrypts communication between the client and server.

## 5. Theory
SSH commonly uses TCP port **22** and supports different authentication methods.

- **Password-Based Authentication:** The user logs in using the remote account password.
- **Key-Based Authentication:** The server verifies the user through a public and private key pair.

The public key is stored on the server, while the private key remains secret on the client. A passphrase can provide additional protection for the private key.

## 6. Visualization

```text
Client                         Remote Server
   | ----- SSH Connection ------> |
   | <--- Server Identification - |
   | -- Password / Public Key --> |
   | <== Encrypted Session =====> |
```

## 7. Results
SSH remote login and password-based and key-based authentication methods were demonstrated or studied, depending on server configuration.

## 8. Discussion
SSH provides encrypted remote access and protects data transmitted between systems. A “Connection refused” error may indicate that the SSH server is not running or not listening on the specified port.

## 9. Improvement
Use strong passwords, protect private keys with a passphrase, keep SSH software updated, and disable password login only after key-based access has been tested successfully.
