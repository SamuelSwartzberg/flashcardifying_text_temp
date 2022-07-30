# cryptosystem

## terms

The plaintext/ciphertext is the message in a readable/unreadable form.
The key is an amount of data (usually a string) which together with the plain/cyphertext and an encryption/decryption function produces cypher/plaintext.
The plaintext/ciphertext/key space is the set of possible plaintexts/ciphertexts/keys.
The encryption/decryption function is the function that does plaintext/cyphertext + key → cyphertext/plaintext
encryption/decryption function ≈ encryption/decryption algorithm
A cipher is a pair of corresponding encryption/decryption functions.

## formal definition

A cryptosystem is a 5-tuple (P, C, K, E, D).
In a cryptosystem P/C/K is the plaintext/ciphertext/key space.
In a cryptosystem E/D is the encryption/decryption function.

## in detail

### keys

For cryptography to be secure, the (relevant) key must not be known.
Key size is the number of bits in the key.

### ciphers

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