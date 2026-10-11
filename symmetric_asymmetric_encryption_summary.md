# Symmetric and Asymmetric Encryption — Study Summary

## Objective
Understand how symmetric and asymmetric encryption work, why key length matters, the algorithms covered in the Google Cybersecurity Certificate reading, and how encryption supports secure communication.

## 1. Core Terms

| Term | Meaning |
|---|---|
| Encryption | Converting readable data into an encoded format |
| Cipher | An algorithm used to encrypt information |
| Public Key Infrastructure (PKI) | A framework used to secure the exchange of online information |
| Plaintext | Readable, unencrypted information |
| Ciphertext | Encrypted information that is not directly readable without the appropriate decryption process |

## 2. Two Main Types of Encryption

### Symmetric encryption
- Uses **one shared secret key** for encryption and decryption.
- Both sender and receiver must know the secret key.
- Commonly used for efficient protection of data.

### Asymmetric encryption
- Uses a **public key and a private key**.
- In the reading's simplified description, the public key encrypts data and the private key decrypts it.
- The private key must remain restricted to authorized users.

| Feature | Symmetric | Asymmetric |
|---|---|---|
| Keys used | One shared secret key | Public/private key pair |
| Key sharing | Secret key must be shared securely | Public key can be shared; private key is kept secret |
| Examples from the reading | AES: 128, 192, 256 bits; 3DES: effective 168 bits | RSA: 1,024, 2,048, 4,096 bits; DSA: 2,048 bits |
| Main consideration | Efficient data encryption; protect the shared key | Supports public-key operations; protect the private key |

**Practical note:** Modern secure connections commonly use asymmetric cryptography to authenticate or establish session keys, then symmetric encryption to protect session data efficiently. Digital signatures and key establishment are distinct from simply encrypting data.

## 3. Why Key Length Matters

A **brute-force attack** tries possible keys until the correct one is found.

- Longer keys generally create more possible combinations and make brute-force attacks harder.
- Longer keys can require more processing.
- Security also depends on the algorithm, implementation, key protection, and configuration.

## 4. Algorithms Covered in the Reading

### Symmetric algorithms

**Triple DES (3DES)**
- A block cipher based on DES.
- Applies the DES algorithm three times.
- The reading describes an effective key length of 168 bits.
- It has limitations and is mainly relevant to legacy compatibility; it should not be selected for new systems.

**Advanced Encryption Standard (AES)**
- A widely used symmetric encryption algorithm.
- Supports 128-bit, 192-bit, and 256-bit keys.
- When appropriately implemented, AES is designed to resist practical brute-force attacks.

### Asymmetric algorithms

**Rivest–Shamir–Adleman (RSA)**
- An asymmetric algorithm using a public/private key pair.
- The reading lists key sizes of 1,024, 2,048, and 4,096 bits.
- For modern deployments, RSA-2048 or stronger is generally preferred; RSA-1024 is no longer considered secure for typical current use.

**Digital Signature Algorithm (DSA)**
- An asymmetric algorithm introduced by NIST.
- The reading describes it as a standard used alongside PKI.
- DSA is primarily a digital-signature algorithm, not a general-purpose data-encryption algorithm; follow current standards and platform support when choosing cryptographic methods.

## 5. OpenSSL and Key Generation

**OpenSSL** is an open-source command-line toolkit used for cryptographic operations, including generating keys and working with certificates.

Security practices:
- Keep OpenSSL and other cryptographic software patched.
- Use supported algorithms and secure configurations.
- Protect private keys and restrict access to them.
- Replace vulnerable or obsolete software versions.

The reading mentions **Heartbleed**, a 2014 OpenSSL vulnerability that could expose sensitive data in application memory. It was patched, illustrating why software updates and vulnerability management matter.

## 6. Kerckhoffs's Principle: Obscurity Is Not Security

A cryptographic system should remain secure even when its algorithm and design are publicly known. Security should depend on protecting the key—not hiding how the algorithm works.

**Takeaway:** Do not rely on a secret, custom-made encryption algorithm as the primary security control.

## 7. How Encryption Is Used Together

A typical secure connection combines cryptographic methods:

```text
Connection setup and authentication
              ↓
Public-key cryptography / key establishment
              ↓
Session key established securely
              ↓
Symmetric encryption protects session data
```

Symmetric encryption is efficient for large amounts of data, while asymmetric cryptography supports tasks such as authentication and key establishment. Exact mechanisms depend on the protocol and configuration.

## 8. Security and Compliance

The reading identifies FIPS 140-3 and GDPR as relevant to cryptographic security and data handling. They serve different purposes:

- **FIPS 140-3** specifies security requirements for cryptographic modules.
- **GDPR** establishes data-protection requirements for covered personal-data processing.

Encryption helps protect confidentiality, but compliance also depends on appropriate policies, access controls, key management, and other safeguards.

## 9. Key Concepts to Remember

- **Symmetric:** one shared secret key.
- **Asymmetric:** public/private key pair.
- **Brute force:** repeatedly trying possible keys.
- **AES:** modern symmetric algorithm with 128-, 192-, and 256-bit key options.
- **3DES:** legacy algorithm; avoid for new deployments.
- **RSA:** asymmetric algorithm used for public-key operations.
- **DSA:** digital signatures, rather than general data encryption.
- **OpenSSL:** toolkit for cryptographic operations and certificate work.
- **Kerckhoffs's principle:** protect the key, not the secrecy of the algorithm.
- **Hybrid encryption:** asymmetric cryptography helps establish/authenticate a session; symmetric encryption protects the data.

## 10. Security Analyst Relevance

When reviewing an environment, a security analyst should ask:

1. Is data encrypted in transit and at rest where required?
2. Are approved, current algorithms and configurations being used?
3. Are obsolete algorithms such as 3DES being phased out?
4. Are private keys and shared secrets protected with restricted access?
5. Is cryptographic software patched and supported?
6. Are certificate validity, renewal, and trust configuration monitored?
7. Do encryption controls support the organization's privacy and compliance requirements?

## Core Takeaway

Encryption protects information by transforming it into a form that unauthorized parties cannot readily understand. Symmetric encryption uses one shared secret key, while asymmetric cryptography uses a public/private key pair. Strong security also depends on sound key management, supported algorithms, secure implementations, and timely software updates.
