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

## process

### key generation

Key generation is the process of generating keys.

### key exchange

#### basics

Key exchange is how all parties get to have the relevant key.

#### the key exchange problem

##### basics

The key exchange problem is the question of how to get the right key from/to the right people.
The key exchange problem may be split into the which key key exchange problem and the which person key exchange problem.

##### which key key exchange problem

###### hybrid cryptosystem

In practice, using public-key security for every message is too slow, so a hybrid cryptosystem is used.
A hybrid cryptosystem uses asymmetric cryptography for key exchange for a subsequently used symmetric cryptography.

###### basics

The which key key exchange problem (my term) is the problem of how to securely acquire the shared symmetric key in a hybrid cryptosystem.

###### key-agreement

A key-agreement protocol is a protocol where key exchange is implemented by getting two parties agree on a key.
A key-agreement protocol that solves the which key key exchange problem is one where both participants influence the outcome, and that does not allow eavesdroppers conclude the key from the transmitted information.

###### diffie-hellman

####### mechanism

Diffie-hellman key exchange/agreement is a key-agreement protocol that solves the which key key exchange problem where 
1. two participants each choose a secret component 
2. both participants agree on an arbitrary public component
3. each participant combines their secret component with the public component, each arriving at their mixture component
4. the participants exchange their mixture components
5. the participants combine their secret component with the other's mixture component
6. thus, the participants arrive at their shared secret

####### modulo

The diffie-helman modulo algorithm is the easiest and original implementation which uses the modulo operation and is based theoretically on modular arithmetic.
For the diffie-helman modulo algorithm, the public component public_modulus must be a prime number, and the public component public_base must be a primitive root modulo public_modulus.

######## diffie-hellman modulo algorithm

1. public components: public_modulus and public_base
2. secret components: arbitrary_integer⎵1/2⎵
3. mixture component⎵1/2⎵ = public_base⎴arbitrary_integer⎵1/2⎵⎴ mod public_modulus
4. the participants exchange their mixture components
5. secret component⎵1/2⎵ =  mixture component⎵2/1⎵⎴arbitrary_integer⎵1/2⎵⎴ mod public_modulus
6. secret component⎵1⎵ = secret component⎵2⎵

##### which person key exchange problem

The which person key exchange problem is the problem that in key exchange, the party one is communicating with is not guaranteed to be the intended recipient, such as in a AitM attack.