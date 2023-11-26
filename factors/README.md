# RSA Encryption Algorithm - README

## Overview

RSA (Rivest–Shamir–Adleman) is a widely used asymmetric cryptographic algorithm that enables secure communication over insecure channels. It is named after its inventors: Ron Rivest, Adi Shamir, and Leonard Adleman. The algorithm is based on the mathematical properties of large prime numbers and their difficulty in factoring the product of two such primes.

This README provides a brief explanation of RSA, its key components, and how it is used for secure communication.

## Key Components

### 1. Key Generation

RSA involves the generation of a public key and a private key:

- **Public Key:** Comprises two components - the modulus (N) and the public exponent (e). The public key is distributed openly and is used for encryption.

- **Private Key:** Comprises two components - the modulus (N) and the private exponent (d). The private key is kept secret and is used for decryption.

### 2. Encryption

1. **Message Representation:** The plaintext message is represented as an integer m.
2. **Encryption Process:** The ciphertext c is calculated using the public key (N, e) as follows: \( c \equiv m^e \mod N \).
3. **Result:** The ciphertext c can be sent securely over the communication channel.

### 3. Decryption

1. **Ciphertext Representation:** The received ciphertext c is represented as an integer.
2. **Decryption Process:** The original message m is calculated using the private key (N, d) as follows: \( m \equiv c^d \mod N \).
3. **Result:** The decrypted message m is obtained.

## Usage

### 1. Key Generation

To generate a pair of RSA keys, use a key generation tool or algorithm. Common key lengths include 1024, 2048, or 3072 bits.

### 2. Encryption

When sending a confidential message:

1. Obtain the recipient's public key (N, e).
2. Represent the plaintext message as an integer m.
3. Calculate the ciphertext c using the encryption formula.

### 3. Decryption

When receiving a ciphertext:

1. Use the private key (N, d) for decryption.
2. Calculate the original message m using the decryption formula.

## Security Considerations

RSA's security relies on the difficulty of factoring the product of two large prime numbers. As computational power increases, it's essential to use sufficiently large key sizes to maintain security.

## Example Code

```python
# Example code for RSA encryption and decryption in Python

# Key Generation
# TODO: Generate RSA keys

# Encryption
def encrypt(message, public_key):
    N, e = public_key
    ciphertext = pow(message, e, N)
    return ciphertext

# Decryption
def decrypt(ciphertext, private_key):
    N, d = private_key
    message = pow(ciphertext, d, N)
    return message
```

## References

- [Original RSA Paper](https://people.csail.mit.edu/rivest/Rsapaper.pdf)
- [PKCS #1: RSA Cryptography Standard](https://tools.ietf.org/html/rfc8017)