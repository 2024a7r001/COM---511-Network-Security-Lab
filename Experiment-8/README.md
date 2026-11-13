# Experiment 8: Send and Receive PGP Encrypted Email Using Thunderbird

## 1. Aim
To send and receive secure emails using PGP encryption and digital signatures in Thunderbird.

## 2. Requirements
- Computer with Mozilla Thunderbird installed
- Email account
- Internet connection

## 3. Methodology

### A. Open Thunderbird

Install and open Mozilla Thunderbird. Set up an email account.

### B. Create OpenPGP Keys

Go to Account Settings and open End-to-End Encryption. Create a new OpenPGP key pair.

### C. Share Public Key

Share your public key with the receiver. Keep your private key secret.

### D. Import Receiver's Public Key

Import the receiver's public key into Thunderbird.

### E. Compose Secure Email

Compose a new email and enable the encryption and digital signature options.

### F. Send and Receive Email

Send the encrypted email. The receiver uses their private key to decrypt and read the message.

## 4. Context

PGP (Pretty Good Privacy) is a security method used to protect emails through encryption and digital signatures. Thunderbird is a free email application that supports OpenPGP encryption.

## 5. Theory

PGP uses public-key cryptography to provide email security.

- **Public Key:** Shared with others to encrypt messages.
- **Private Key:** Kept secret and used to decrypt messages.
- **Encryption:** Protects the confidentiality of email messages.
- **Digital Signature:** Verifies the sender and ensures message integrity.

The sender uses the receiver's public key for encryption, and the receiver uses their private key for decryption.

## 6. Visualization

```text
Sender                         Receiver
   |                               |
   | --- Public Key -------------> |
   |                               |
   | --- Encrypted Email --------> |
   |                               |
   | <--- Decrypt using ----------- |
   |       Private Key             |
   |                               |
   | <== Secure Email ===========> |
```

## 7. Results

Successfully demonstrated sending and receiving PGP-encrypted and digitally signed emails using Thunderbird.

## 8. Discussion

PGP provides confidentiality, authentication and integrity for email communication. Thunderbird makes it easier to create keys, encrypt messages and verify digital signatures.

## 9. Improvement

Keep private keys secure, use strong passphrases, verify public keys before trusting them, and regularly back up important encryption keys.
