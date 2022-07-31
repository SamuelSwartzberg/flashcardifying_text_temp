# layer 3

The ping utility uses the ICMP protocol's mandatory ECHO_REQUEST datagram to elicit an ICMP ECHO_RESPONSE from an IP.
the main protocol that lives on the network (OSI)/internet (TCP/IP) layer is IP.

## IP

IP  Internet protocol
IP has the task of delivering packets from the source host to the destination host solely based on the IP addresses in the packet headers.
IP (in general) works because connected routers know where packages starting with a certain IP routing/network prefix should go, and so on

the ⟮host URL element⟯ for the ⟮loopback address⟯ is usually ⟮localhost⟯
the IP protocol data unit (the packet) is alternatively sometimes also called datagram.

### hops

flex-container:✫Hop-count-trans.png✫


A ⟮hop⟯ occurs every time a ⟮packet⟯ is ⟮passed from one network to the next⟯. 
The ⟮hop⟯ count is thus a rough measure of ⟮distance between devices⟯.

### address space

flex-container:✫1024px-Regional_Internet_Registries_world_map.svg.png✫

RIR = Regional Internet Registry
NRO = Number Resource Organization
There are 5 RIRs.
the 5 RIRs are affiliated via the NRO
5 RIR areas:, one for Africa, most of NA, latin and central america + Mexico, Europe + Russia/West Asia, and one for most of Asia + Oceania

### headers

the ⟮IPv4 header⟯ consists of ⟮14⟯ ⟮different fields⟯
TTL = Time To Live
TTL in IPv4 contexts was supposed to measure seconds, but was actually implemented as a hop count.
TTL as hop count was implmeneted by an 8-bit integer, usually starting at 64. When it reached 0, the packet was discarded and an ICMP time exeeded message was typically sent.
TTL exists amongst other reasons to prevent an infinite routing loop.
⟮TTL⟯ is called ⟮hop limit⟯ in ⟮IPv6⟯

### addr

#### IPv

The first major version of IP was IPv4, which is being succeeded by IPv6
The main reason IPv6 was introduced is that there are not enough IPv4 addresses
While IPv4 was written in dot-decimal, IPv6 is most commonly written in hexadecimal

IPv4|32
IPv6|128

IPv4-addr = 1*3DIGIT "." 3("." 1*3DIGIT)

##### IPv6

An IPv6 address consists of 8 quibbles.
the ⟮quibbles/hextets/hexadectets/quad-nibbles⟯ of a IPv6 address are separated by ⟮colons⟯
within an IPv6 address, ⟮consecutive quibbles⟯ of ⟮only zeroes⟯ may be ⟮replaced with `:­:`⟯, but only ⟮once in an address⟯, and not for ⟮a single quibble⟯
within an ⟮IPv6 address⟯, within a ⟮quibble⟯, any ⟮leading⟯ ⟮zeroes⟯ may be ⟮removed⟯
because of possible ambiguity of having colons within the host of URLs, when within URLs, IPv6 addresses should be enclosed in square brackets
```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

#### division

IP addresses have always been divided between network prefix and host identifier.
network prefix is also called routing prefix
host identifier is also called rest field or interface identifier
How network prefix and host identifier have been divided has varied over time
The subnet mask is the bitmask that when applied with bitwise AND yields the network prefix.
The subnet mask is also often written in the notation of IP addresses.
using CIDR notation, the subnet mask of whatever.whatever.whatever.0/24 is 255.255.255.0

##### History

In the very beginning (until the 1980s) IP addresses were divided between the first octet as network prefix and the last 3 octets as host identifier.
In the very beginning (until the 1980s) what we call network prefix was called network number, and what we call host identifier was called rest field.
In the early 80s, IP addresses transitioned to classful IP addresses.
In classful IP addresses, there were different classes, which each had different network prefixes and host identifiers of different lengths.
In classful IP addresses, the first or first few bits would have indicated which class it was, the next however many relevant numbers would have been the network prefix, and finally the host identifier
One of the major problems with classful IP addresses was that the host identifier namespace was either to small or too large (either ~65k or ~16 million addresses)


table:Class|bit header|networ prefix length
A|1⎵2⎵|1 byte
B|10⎵2⎵|2 byte
C|110⎵2⎵|3 byte
-|111⎵2⎵|〜4 lol〜 first unused, later multicast addressing


⟮Classful IP addresses⟯ were used until ⟮the early 90s⟯ (⟮1993⟯) and then replaced with ⟮Classless Inter-Domain Routing⟯ (⟮CIDR⟯)


##### CIDR

CIDR = Classless Inter-Domain Routing
cidr-notation ::= [‹IPv4-addr›]/‹int-0-32›
⟮CIDR notation⟯ indicates ⟮the length⟯ of ⟮the network prefix⟯ (equivalently: ⟮the amount of leading 1-bits⟯ of the ⟮network mask⟯) as an ⟮integer⟯, normally ⟮after the IP address⟯ separated by ⟮a `/`⟯
if CIDR notation is used with no IP address, it describes networks with the relevant split between network prefix and host identifier
/24 = an IPv4 network that has a 24-bit newtwork prefix and 8-bit host identifiers
Using CIDR, to indicate a super/subnet/CIDR block, you may either use the network identifier address (e.g. 198.51.0.0/16), or only include the filled bits of the address (198.51/16)
198.51.100.14/24 is saying that this address has a network prefix of 24 bit length (198.51.100) and a host identifier of 8 bit (14)

###### CIDR blocks

flex-container:✫sm_cidr_addr.svg✫

A CIDR block is a group of IP addresses sharing the same network/routing prefix.
⟮CIDR Blocks⟯ ≈ ⟮network/routing prefixes⟯ may be ⟮further subdivided⟯, with ⟮more and more⟯ of the IP address being looked at to ⟮direct the traffic⟯
A CIDR block A which is completely contained within another CIDR block B is a subnet of B, B is a supernet of A.
All networks are implicitly subnets of the IP address space.
a ⟮supernet(work)⟯ has a ⟮shorter⟯ ⟮network prefix⟯, whose ⟮subnets⟯ will have a ⟮longer⟯ ⟮network prefix⟯ that ⟮starts with⟯ the ⟮supernet⟯  ⟮network prefix⟯ 
Note: Not all possible CIDR block sub/supersets are actual sub/supernets!
The process of forming a supernet is called supernetting or prefix/route aggregation/summarization
the largest ⟮CIDR block (= sub/supernet)⟯ the IANA assigns is ⟮/8⟯ (⟮16 million⟯ addresses)

##### broadcast ＆ network identifier

A ⟮subnet/CIDR block⟯'s ⟮broadcast⟯ address is the ⟮all-ones⟯ version of the ⟮host (any relevant IP address)/network (all-zeroes) identifier⟯
A ⟮subnet/CIDR block⟯'s ⟮network identifier⟯ address is the ⟮all-zeroes⟯ version of the ⟮host identifier⟯
The network identifer address is often functionally treated as the broadcast address.
The network identifier address of 173.240.0.0/16 is 173.240.0.0
The broadcast address of 173.240.0.0/16 is 173.240.255.255.

###### max broadcast and max identifier

Ergo, 255.255.255.255 (/0) is (theoretically) the broadcast address to all IP addresses in existence.
A godzillagram is theoretically a message to 255.255.255.255, which should theoretically broadcast to all IP addresses in existence.
Since gateways generally do not let godzillagrams pass, 255.255.255.255 generally merely boradcasts to your whole network.
Since network identifier addresses are generally aliases to broadcast addresses, 0.0.0.0/0 is an alias to the broacast address 255.255.255.255/0.
0.0.0.0/32 represents the undefined/NULL address, and may be used when one has not yet aquired an IP address or when accepting all incoming connections.

##### special IP addresses

all IP adresses with the CIDR notation ⟮127.0.0.0/8⟯ (⟮127.0.0.1⟯ - ⟮127.255.255.254⟯, excluding ⟮network identifier⟯ and ⟮broadcast addresses⟯) are ⟮loopback⟯ addresses
of the IPv4 loopback addresses, generally 127.0.0.1 is used.
localhost = 127.0.0.1 (IPv4)
IPv6 reserves only a single loopback address, which is ­:­:1

The private IPv4 address blocks sorted from largetst to smallest are: ⟮10.0.0.0⟯/⟮8⟯, ⟮172.16.0.0⟯/⟮12⟯, ⟮192.168.0.0⟯/⟮16⟯
(100000 = Prof X dual-wielding dual swords, 172160 = Android 17 outrunning a caravan of refugees, 192168 = Anakin skywalker outrunning a dragon)
a private network is a computer network that uses a private address space of IP addresses, most often used for LANs

### NAT

NAT = Network Address Translation
⟮NAT⟯ ⟮maps one IP address space to another⟯ by ⟮modifying the info in the IP header⟯
NAT could be one-to-one or one-to-many, generally one-to-many is implied
For one-to-many NAT, most commonly the combination of IP address and port number is sued to unabiguously identify the reciver.
For one-to-many NAT, the client port is additionally used disambiguate the reciever (which is possible since the client port is arbitrary anyway)
NAT (Network Address Translation)  allows mitigation of IPv4 address exhaustion because one IP address can be used for an entire network
the form of NAT where ⟮the combination of IP address and port number is used to identify the recipient⟯ may also be known as ⟮NAPT⟯ (⟮network address and port translation⟯) , ⟮PAT⟯ (⟮port address translation⟯) or ⟮IP masquerading⟯ amongst others

### tracing

traceroute and tracepathe are *nix utilities to measure IP paths and transit durations.
⟮tracepath⟯ is a ⟮non-superuser⟯ version of ⟮traceroute⟯
tracepath/traceroute sends messages with adjusted TTL values and uses ICMP time exceeded messages to identify the routers traversed by packets from the source to the destination.

### ICMP

ICMP = Internet Control Message Protocol
ICMP is used to send IP/routing-related error/control message.
ICMP messages are sent within an IP packet