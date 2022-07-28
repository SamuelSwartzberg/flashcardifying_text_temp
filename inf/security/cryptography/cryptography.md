# cryptography

Cryptography is the study of cryptosystems and everything related to them.
Cryptographic security/authentication (rareish terms) is the use of cryptosystems for the purpose of secure communication/authentication.

## cryptosystem

### terms

The plaintext/ciphertext is the message in a readable/unreadable form.
The key is an amount of data (usually a string) which together with the plain/cyphertext and an encryption/decryption function produces cypher/plaintext.
The plaintext/ciphertext/key space is the set of possible plaintexts/ciphertexts/keys.
The encryption/decryption function is the function that does plaintext/cyphertext + key → cyphertext/plaintext
encryption/decryption function ≈ encryption/decryption algorithm
A cipher is a pair of corresponding encryption/decryption functions.

### formal definition

A cryptosystem is a 5-tuple (P, C, K, E, D).
In a cryptosystem P/C/K is the plaintext/ciphertext/key space.
In a cryptosystem E/D is the encryption/decryption function.

### in detail

#### keys

For cryptography to be secure, the key must not be known.
Key generation is the process of generating keys
Key exchange is how all parties get to have the relevant key.
Key size is the number of bits in the key.

#### ciphers

A substitution cipher is a cipher where an unit of plaintext is replaced by an unit of cipher text
The caesar cipher is a kind of substitution cipher where the replacement is done by rotating the entire alphabet by some number.

## symmetric and asymmetric

An symmetric/asymmetric(-key) cipher is a cipher that consists of a pair of encryption & decryption algorithms that both take the same key/take a different key for encryption and decryption.
An symmetric/asymmetric(-key) algorithm is an encryption or decryption algorithm of an symmetric/asymmetric(-key) cipher.
A symmetric/asymmetric key is the/a key used in an symmetric/asymmetric cipher.
Mathematically, an asymmetric-key algorithm is implemented via a one-way function.
Symmetric/asymmetric cryptography is cryptography using symmetric/asymmetric-key ciphers.
A reciprocal cipher is a cipher where the encryption/decryption function is the same.
^not all symmetric cyphers are reciprocal ciphers

### public-key cryptography

#### basic

public-key cryptography is asymmetric cryptography where the two asymmetric keys are used as public/private keys.
A public/private key is the asymmetric key which should be shared widely/kept secret.
A key pair is a set of public & private keys.
The sender/recipient key pair is the key pair of the sender/recipient.

#### digital signing

Public-key security/authentication is the use of public-key cryptography for cryptographic security/authentication.
In public-key security/authentication, the only key pair involved is the sender/recipient key pair.
In public-key security, the message is encrypted with the recipient's public key and decrypted with the recipient's private key.
In public-key authentication, the message is encrypted with the sender's private key and decrypted with the sender's public key.
^this proves the authenticity since only the sender should have their private key, and something encrypted with the sender's private key should only be able to be decrypted with the sender's public key.
Digital signing =syndef= public-key authentication.

### hybrid

A hybrid cryptosystem uses asymmetric cryptography for key exchange for a subsequently used symmetric cryptography.
^nearly uniersal today (e.g. TLS, SSH)
The key exchange problem is the difficulty of transmitting a 
A hybrid cryptosystem solves the key exchange problem.