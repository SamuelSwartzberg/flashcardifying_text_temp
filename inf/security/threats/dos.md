# DoS

DoS/DDoS =short for=> denial of service/distributed denial of service
A DoS attack seeks to make a thing unavailable.
A resource exhaustion/non-exhausting DoS attack (rare terms, have polysemy) is a DoS attack that works by exhausting resources/doing something else.

## resourse exhaustion DoS attack

### DDoS

A DDoS attack is a resource exhaustion DoS attack performed from many different sources.

### types

#### low and slow

A low and slow attack is a resource exhaustion DoS attack using a small stream of very slow traffic.

##### slowloris

A slowloris attack is a low and slow attack that opens as many connections as possible and sends a few bytes of the HTTP header section every now and then, but never sends the header section end CRLF CRLF.
A slowloris attack works if the server uses a fairly limited resource, e.g. threads, for each incoming request.