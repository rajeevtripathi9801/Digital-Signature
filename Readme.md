# Secure Communication Project

This project demonstrates a secure connection between a client and server where data is sent in an encrypted manner. It implements simplified versions of AES (Advanced Encryption Standard), RSA (Rivest–Shamir–Adleman), and Digital Signature generation and verification using Python and socket programming.

## Project Overview

![Architecture.png](https://github.com/tripathiraj981/Digital-Signature/blob/main/Architecture.png)

*Figure 1: High-level architecture of the Secure Communication Project*

## Features

- RSA encryption and decryption
- AES encryption and decryption
- Digital Signature generation and verification using SHA-256
- Socket programming to establish a local server-client connection

## Libraries Used

```python
import asyncio
import sys
import websockets
import threading
import numpy as np
import json
import hashlib
```

## Implementation Details

### RSA Implementation

The RSA implementation includes the following key functions:

1. `generatekeypair()`: Generates public and private key pairs for given prime numbers 'p' and 'q'.
2. `r_encrypt()`: Encrypts a message using two inputs: key and message.
3. `r_decrypt()`: Decrypts a message using two inputs: key and message.
4. `isprime()`: Checks if a number is prime.

Additional features:
- Uses `hashlib` to generate a hexadecimal digest for digital signatures.
- Encrypts the cipher key at the client-side using the public key received from the server.
- Decrypts the cipher key at the server-side using the server's private key.

### AES Implementation

![demo (1)](https://github.com/tripathiraj981/Digital-Signature/blob/main/demo%20(1).png)

![Demo 2](https://github.com/tripathiraj981/Digital-Signature/blob/main/demo%20(2).png)

*Figure 2: Simplified AES encryption process*

The Simplified AES (S-AES) implementation includes:

1. Key Generation:
   - `keyExp()`: Generates sub-keys.
   - `Sub2Nib()`: Applies S-Box substitution on nibbles using the encryption S-Box.

2. Message Encryption and Decryption:
   - Encryption goes through two rounds and returns ciphertext.
   - Decryption reverses the process to retrieve the original plaintext.

## Project Flow

1. Run `server.py`
2. Run `client.py`
3. Enter required information (plaintext, keys) in the client.
4. Observe the encryption, transmission, and decryption process.
5. Verify that the decrypted plaintext matches the original and that the digital signature is verified.

## Detailed Process Overview

1. **RSA Key Generation**:
   - User enters prime numbers p and q.
   - Public key (e, n) and private key (d, n) are generated for both server and client.

2. **Digital Signature**:
   - A digest is generated using SHA-256.
   - The digest is used to create a digital signature.

3. **Signature Verification**:
   - The server decrypts the signature and verifies it against the original message.

4. **AES Encryption**:
   - Client enters a 16-bit plaintext and a key.
   - Plaintext is encrypted using the AES algorithm.

5. **Data Transmission**:
   - Encrypted data (ciphertext) is sent from client to server using socket programming.

6. **AES Decryption**:
   - Server receives the ciphertext and decrypts it using the AES algorithm.

7. **Verification**:
   - The system checks if the decrypted plaintext matches the original message.
   - The digital signature is verified.

## Output

The program will display various intermediate steps and finally confirm:
- "Plaintext and Original are same"
- "The decryption worked and signature is verified!"

## Future Improvements

- Add error handling and input validation
- Implement a graphical user interface (GUI)
- Extend to support file encryption and decryption
- Enhance security measures and implement proper key management

