# COM 511 – Network Security Lab

## Generate and Verify X.509 Self-Signed Digital Certificate

### Aim

To generate and verify a self-signed X.509 digital certificate using OpenSSL and understand its role in secure communication.

### Methodology

* Generate a 2048-bit RSA private key.
* Create a self-signed X.509 certificate.
* Inspect the certificate structure.
* Verify the certificate using OpenSSL.
* Observe Subject, Issuer, Public Key and Validity.

### Context

Digital certificates are used in HTTPS/TLS to identify a server and support secure communication. A self-signed certificate is mainly useful for testing, learning and local development.

### Theory

An X.509 certificate contains:

* **Subject** – Identity of the certificate owner.
* **Issuer** – Entity that issued the certificate.
* **Public Key** – Used for cryptographic operations.
* **Validity** – Certificate start and expiry date.
* **Digital Signature** – Used to verify the certificate.

In a self-signed certificate, the certificate is signed by its own private key.

### OpenSSL Commands

```bash
# Generate private key
openssl genrsa -out server.key 2048

# Generate self-signed certificate
openssl req -x509 -new -key server.key -sha256 -days 365 -out server.crt

# Inspect certificate
openssl x509 -in server.crt -text -noout

# Verify certificate
openssl verify -CAfile server.crt server.crt

# Display Subject and Issuer
openssl x509 -in server.crt -noout -subject -issuer
```

### Visualization

```text
Private Key
     ↓
Self-Signed X.509 Certificate
     ↓
Inspect → Verify
     ↓
HTTPS / TLS Secure Communication
```

### Result

The 2048-bit RSA private key and self-signed X.509 certificate were successfully generated. The certificate was inspected and successfully verified with the result:

```text
server.crt: OK
```

The Subject, Issuer, Public Key and Validity information were also observed.

### Discussion

The experiment demonstrated the basic working of an X.509 digital certificate using OpenSSL. A self-signed certificate can be used for testing and local HTTPS/TLS communication, but it is not automatically trusted by public browsers.

### Improvement

* Add Subject Alternative Name (SAN).
* Use the certificate with a local HTTPS server.
* Create a private Certificate Authority (CA).
* Test certificate validation using a browser or TLS client.


