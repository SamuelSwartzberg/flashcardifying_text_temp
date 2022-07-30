# theory

## basic

public-key cryptography is asymmetric cryptography where the two asymmetric keys are used as public/private keys.
A public/private key is the asymmetric key which should be shared widely/kept secret.
A key pair is a set of public & private keys.
The sender/recipient key pair is the key pair of the sender/recipient.

## security and authentication

Public-key security/authentication is the use of public-key cryptography for cryptographic security/authentication.
In public-key security/authentication, the only key pair involved is the sender/recipient key pair.
In public-key security, the message is encrypted with the recipient's public key and decrypted with the recipient's private key.
In public-key authentication, the message is encrypted with the sender's private key and decrypted with the sender's public key.
^this proves the authenticity since only the sender should have their private key, and something encrypted with the sender's private key should only be able to be decrypted with the sender's public key.
Digital signing =syndef= public-key authentication.
