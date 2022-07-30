
# process

## key generation

Key generation is the process of generating keys.

## key exchange

### basics

Key exchange is how all parties get to have the relevant key.

### the key exchange problem

#### basics

The key exchange problem is the question of how to get the right key from/to the right people.
The key exchange problem may be split into the which key key exchange problem and the which person key exchange problem.

#### which key key exchange problem

##### hybrid cryptosystem

In practice, using public-key security for every message is too slow, so a hybrid cryptosystem is used.
A hybrid cryptosystem uses asymmetric cryptography for key exchange for a subsequently used symmetric cryptography.

##### basics

The which key key exchange problem (my term) is the problem of how to securely acquire the shared symmetric key in a hybrid cryptosystem.

##### key-agreement

A key-agreement protocol is a protocol where key exchange is implemented by getting two parties agree on a key.
A key-agreement protocol that solves the which key key exchange problem is one where both participants influence the outcome, and that does not allow eavesdroppers conclude the key from the transmitted information.

##### diffie-hellman

###### mechanism

Diffie-hellman key exchange/agreement is a key-agreement protocol that solves the which key key exchange problem where 
1. two participants each choose a secret component 
2. both participants agree on an arbitrary public component
3. each participant combines their secret component with the public component, each arriving at their mixture component
4. the participants exchange their mixture components
5. the participants combine their secret component with the other's mixture component
6. thus, the participants arrive at their shared secret

###### modulo

The diffie-helman modulo algorithm is the easiest and original implementation which uses the modulo operation and is based theoretically on modular arithmetic.
For the diffie-helman modulo algorithm, the public component public_modulus must be a prime number, and the public component public_base must be a primitive root modulo public_modulus.

####### diffie-hellman modulo algorithm

1. public components: public_modulus and public_base
2. secret components: arbitrary_integer⎵1/2⎵
3. mixture component⎵1/2⎵ = public_base⎴arbitrary_integer⎵1/2⎵⎴ mod public_modulus
4. the participants exchange their mixture components
5. secret component⎵1/2⎵ =  mixture component⎵2/1⎵⎴arbitrary_integer⎵1/2⎵⎴ mod public_modulus
6. secret component⎵1⎵ = secret component⎵2⎵

#### which person key exchange problem

##### basics

The which person key exchange problem is the problem that in key exchange, the party one is communicating with is not guaranteed to be the intended recipient, such as in a AitM attack.

##### public key infrastructure

###### basics

Public key infrasturcture is the set of infrastructure is the infrastructure that manages public key certificates and things related to them.

###### certificates

####### basics

A public key certificate is a document aiming to prove the validity of a public key, mainly via the digital signature of a CA's private key, thus solving the which person key exchange problem.
A public key certificate typically consists of information about the key & how it is to be used, information about the identity of the owner, and a digital signature (with the CA's private key).
digitial/identity certificate =syndef= public key certificate

####### misc

The public key subject is the owner of the certificate.
A server/client certificate is a public key certificate of a client/server.
Certificate verification is the process of verifying a public key certificate.

####### X.509

######## basics

X.509 is a standard defining the format of public key certificates and related things.
A X.509 certificate is a public key certificate conformant with X.509
There are 3 versions of X.509 certificates.
RFC 1422 standartizes version 1 of the X.509 certificates.

######## RFC 1422/X.509 certificate v1 

RFC 1422/X.509 certificate v1 consists of the version, serial number as well as information about the subject, issuer, validity period (this grouping is mine).
For RFC 1422/X.509 certificate v1 the information about the subject consists of subject name and subject private key information
For RFC 1422/X.509 certificate v1 the information about the issuer consists of issuer name and signature information.
For RFC 1422/X.509 certificate v1 the validity period consists of not before and not after.
For RFC 1422/X.509 certificate v1 the subject public key information/signature information consists of the public key/signature and an algorithm identifier.

######## relationships

The issuer name is the subject name of the parent certificate.
The signature is the public key of the the parent certificate.

####### files

######## common formats

For things related to public-key cryptography, typically the file formats used PEM, DER, but also others.

######## PEM

######### basics

Privacy-Enhanced Mail =short=> PEM 
A PEM file is a file that can contain basically any data, but is primarily used to store things related to public-key cryptography.
What kind of data is stored within a pem-textualmsg is identified by conventional pem-labels.
^that's it's origin, though today it's independent from its origins

######### syntax

pem-file ::= {&lt;pem-textualmsg&gt;}
pem-textualmsg ::= &lt;pem-header&gt;&lt;pem-base64text&gt;&lt;pem-footer&gt;
pem-header/footer ::= -----BEGIN/END &lt;pem-label&gt; -----&lt;EOL&gt;

######### contents

If a pem-textualmsg is storing a certificate/certificate request/private key, the pem-label is CERTIFICATE/CERTIFICATE REQUEST/PRIVATE KEY

######## extensions

a DER・PEM file may have the extensions, .der・.pem, .cer/.crt/.cert or .key, ostensibly depending on whether the data inside is generic, a certificate, or a private or public key

###### trust model

a hierarchy/web of trust is a public key infrastructure relying on a hierarchical relationship for solving the which person key exchange problem.

####### hierarchy of trust

A hierarchy of trust is built on the certificate chain.

######### certificate chain

Certificate verification requires the public key certificate to have a certificate chain that goes back to a trusted CA.
The certificate chain (of trust) is the link of parent certificates.
A parent certificate is a certificate that was signed by their parent certificate authority.

########## certificates along the chain

A root/intermediate certificate is a public key certificate that is self-signed/signed by a parent certificate authority and isn't a end-user certificate.
A root/intermediate CA is a CA that issues root/intermediate certificates.
An end-user certificate is a public key certificate that is the leaf of the certificate chain, used by the host one is communicating with.

######### certificate authorities

A certificate/certification authority is an entity that stores/signs/issues public key certificates.
CA =short for=> certificate/certification authority.

########## who signs

A self-signed/CA(-signed) certificate is a public key certificate signed by some entity themselves/by a CA.
A self-signed certificate provides no extra safety for the which person key exchange problem, and therefore should be limited to root CAs and non-production environments.

######### trust

A trusted certificate is a root certificate that comes preinstalled with a piece of hardware or software.
The (trusted) certificate list/store is the place where trusted CA certificates are stored.
A trusted CA is a CA with a trusted certificate installed.

########## examples

Common commercial root CAs are IdentiTrust and DigiCert.
Let's Encrypt is by far the largest non-commercial root CA.

To introduce ads into encrypted sites, lenovo added a self-signed trusted certificate to all computers, which then allowed anyone to sign their certificates with the that trusted certificate's private key, 



