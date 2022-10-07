## symmetric vs asymmetric encryption

Topics: [[security+]] [[cybersecurity]]  

---
# Symmetric Vs Asymmetric Encryption

## Symmetric Encryption (shared key)
- Uses a single key to encrypt and decrypt the data.
- Is more straightforward and conventional method of encryption.
- Is faster when compared to asymmetric encryption, thanks to its simplicity.
- Requires smaller key lengths, usually of 128-256 bit length.
- Provides the confidentiality of the data (data security).
- Is useful for encrypting a large amount of data.  
Source: https://sectigostore.com/blog/types-of-encryption-what-to-know-about-symmetric-vs-asymmetric-encryption/

A cryptographic algorithm that uses a **single secret key** for different operations, such as for encryption and decryption. 
Source: https://csrc.nist.gov/glossary/term/symmetric_key_algorithm

Symmetric encryption is a type of encryption where only one key (a secret key) is used to both encrypt and decrypt electronic information. The entities communicating via symmetric encryption must exchange the key so that it can be used in the decryption process.  

**Two types of symmetric encryption algorithms:**
1. Block algorithms. Set lengths of bits are encrypted in blocks of electronic data with the use of a specific secret key. As the data is being encrypted, the system holds the data in its memory as it waits for complete blocks.  
2. Stream algorithms. Data is encrypted as it streams instead of being retained in the system’s memory.  
Source: https://www.cryptomathic.com/news-events/blog/symmetric-key-encryption-why-where-and-how-its-used-in-banking

**Examples of symmetric encryption**
- Data Encrpytion Standard (DES) *block cipher*
- Triple Data Encryption Standard (Triple DES or 3DES) *block cipher*
- Advanced Encryption Standard (AES) *block cipher*
- International Data Encryption Algorithm (IDEA) *block cipher*
- Blowfish (Drop-in replacement for DES or IDEA) *block cipher*
- Rivest Cipher 4 (RC4) *stream cipher*
- Rivest Cipher 5 (RC5) *block cipher*
- Rivest Cipher 6 (RC6) *block cipher*

## Asymmetric Encryption (public key cryptography)
- Uses two separate keys for encryption and decryption. They’re known as “public key” and “private key.”
- Was invented to mitigate the risks of symmetric encryption and is more complicated.
- Is slower and requires more computational power because of its complexity.
- Asymmetric keys are longer in their lengths.
- Provides confidentiality, authenticity, and non-repudiation.
- Is useful for encrypting a small amount of data.  
Source: https://sectigostore.com/blog/types-of-encryption-what-to-know-about-symmetric-vs-asymmetric-encryption/

Cryptography that uses two separate keys to exchange data, one to encrypt or digitally sign the data and one for decrypting the data or verifying the digital signature. Also known as public key cryptography.
Source: https://csrc.nist.gov/glossary/term/asymmetric_cryptography

**Examples of asymmetric encryption**
- Rivest–Shamir–Adleman (RSA)
- Diffie-Hellman (DH)
- Elliptic-curve cryptography (ECC)
- Digital Signature Algorithm (DSA)
