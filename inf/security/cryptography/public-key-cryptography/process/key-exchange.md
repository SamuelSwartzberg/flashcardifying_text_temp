# key exchange

## basics

Key exchange is how all parties get to have the relevant key.

## hybrid cryptosystem

In practice, using public-key security for every message is too slow, so a hybrid cryptosystem is used.
A hybrid cryptosystem uses asymmetric cryptography for key exchange for a subsequently used symmetric cryptography.

## the key exchange problem

The key exchange problem is the problem of how to securely acquire the shared symmetric key in a hybrid cryptosystem.

## key-agreement

### basics

A key-agreement protocol is a protocol where key exchange is implemented by getting two parties agree on a key.
A key-agreement protocol that solves the which key key exchange problem is one where both participants influence the outcome, and that does not allow eavesdroppers conclude the key from the transmitted information.

### diffie-hellman

#### mechanism

Diffie-hellman key exchange/agreement is a key-agreement protocol that solves the which key key exchange problem where 
1. two participants each choose a secret component 
2. both participants agree on an arbitrary public component
3. each participant combines their secret component with the public component, each arriving at their mixture component
4. the participants exchange their mixture components
5. the participants combine their secret component with the other's mixture component
6. thus, the participants arrive at their shared secret

#### modulo

The diffie-helman modulo algorithm is the easiest and original implementation which uses the modulo operation and is based theoretically on modular arithmetic.
For the diffie-helman modulo algorithm, the public component public_modulus must be a prime number, and the public component public_base must be a primitive root modulo public_modulus.

##### diffie-hellman modulo algorithm

1. public components: public_modulus and public_base
2. secret components: arbitrary_integer⎵1/2⎵
3. mixture component⎵1/2⎵ = public_base⎴arbitrary_integer⎵1/2⎵⎴ mod public_modulus
4. the participants exchange their mixture components
5. secret component⎵1/2⎵ =  mixture component⎵2/1⎵⎴arbitrary_integer⎵1/2⎵⎴ mod public_modulus
6. secret component⎵1⎵ = secret component⎵2⎵