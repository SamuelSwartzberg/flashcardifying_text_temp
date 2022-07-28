# cryptanalysis

Cryptanalysis is the part of cryptography concerned with attempts to accesss the contents of encrypted messages.
A cryptanalytic attack is an attempt at cryptanalysis.
Cryptanalytic attacks may be cryptographic algorithm attacks,  side-channel attacks or guessing attacks.
A cryptographic algorithm/side-channel attack is a cryptanalytic attack that exploits a weakness in the algorithm/in the implementation or something else.

## side-channel attack

### communication attack

A communication attack (my term) is a side-channel attack on the communicatioon between two agents.

#### MitM attack

flex-container:✫sm_mitm_illus.svg✫


A ⟮adversary/man/monster/machine/monkey/meddler/person-in-the-middle⟯ attack is when an attacker secretly relays and possibly alters the communication between two parties believing to be interacting with each other.

##### replay attack

A replay attack is a adversary-in-the-middle attack where the attacker intercepts the message, and then does something with it at a later time.
A delay/repeat replay attack is a replay attack where the attacker sends the original message, but at a later time/sends the original message, and then resends it at a later time.
Replay attacks are often used on authentication messages.

## guessing attack

A guessing attack is a cryptanalytic attack that attempts to try out possible answers until the correct one is reached.
A brute-force/dictionary attack is a guessing attack that tries the entire keyspace/a logically limited keyspace.
