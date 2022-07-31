
### network admin tools

ifconfig is a linux tool to configure networke interfaces, though it is often deprecated in favor of iproute2.
iproute2 collects a bunch of legacy networking commands into a few commands, the most important of which are ip and tc.
speedtest-cli test the speed of your connection

### model comparison

#### models

The OSI model remains useful, but unimplemented.
In both the OSI and the TCP/IP Model of how computers communicate, the application layer is the ⟮top⟯ layer.
Internet protocol suite = TCP/IP
The internet protocol suite is a protocol stack
Instead of the OSI model, the TCP/IP model is used to model the communication on the internet today.
One of the first networks to implement the ⟮TCP/IP protocol suite⟯ and one of the precursors to ⟮the internet⟯ was ⟮ARPANET⟯

#### layers

table:OSI Model|TCP/IP Model|PDU (TCP/IP)|Communicant identifier
Application|span=1,3;Application||path of URL (I think)
Presentation
Session
Transport|Transport|segment (TCP) / datagram (UDP)|Port
Network|Internet|Packet|IP Address
Data Link|Link|frame|MAC Address
Physical

Frame contains IP packets contains segment/datagram contains application protocol message

TCP/UDP segments/datagrams are transmitted in IP packets between hosts.
IP packets are transfered in frames between routers.

table:style=table-layout: fixed;|||style=background-color: #9f9;Data||type=th;⟮c+;s∞;Application⟯
||style=background-color: #d8b;UDP / TCP header|style=background-color: #8d8;(UDP / TCP) data||type=th;⟮c+;s∞;Transport⟯
|style=background-color: #87e;IP header|span=2;style=background-image: linear-gradient(to right, #b7a 50%, #8d8 50%);(IP) data||type=th;⟮c+;s∞;Internet⟯
style=background-color: lightsalmon;Frame header|span=3;style="background-image: linear-gradient(to right, #87e 33%, #d8b 33% 66%, palegreen 66%);(Frame) data|style=background-color: lightsalmon;Frame footer|type=th;⟮c+;s∞;Link⟯

#### hardware

layer no|layer name|device that moves things here
3|Network/Internet|Router
2|Data Link|Switch, Bridge, WAP
1|Physical|hub

WAP|Wireless Access Point

Network hubs act to connect a network on the physical layer by mirroring an incoming signal to all other ports, thus seeming like a directly connected network on the data link layer.
Network bridges/switches act to connect multiple link-layer network segments, which thus aggregates them to a single network on the network/internet layer.
A wireless bridge is a network bridge used for wireless networks.
A network switch is a multiport network bridge.
A network switch uses the MAC addresses to make sure that the the frame is sent to only the host that needs it.
Routers pack IP packets into frames and forwards those to the next router.
A ⟮wireless router⟯ performs the functions of ⟮a router⟯ and of ⟮a wireless acces point⟯ (and sometimes others as well)
Most commonly, a ⟮(network) gateway⟯ is a ⟮router⟯ that ⟮provides access to (acts as a door to) a local network⟯, but the term may also ⟮refer to a bunch of other things⟯
If a (normal office/home) computer user wants to load a web page, at least two network gateways are accessed—one to get from the office or home network to the Internet and one to get from the Internet to the computer that serves the web page.

While you may have as many Switches, bridges, and hubs as you like, to connect to the internet at large, you'll need a router.

Multilayer switches are switches that don't just operate on the data link layer, but also on higher layers (generally 3 and/or 4).
Content switches are multilayer switches that operate up to layer 7, and are often used in CDNs

The function of a firewall is to filter  incoming network traffic.
a firewall filters network traffic according to a variety of rules, the most basic of which might be blocking most ports unless needed
A firewall generally operates on the network/internet layer and up.

##### alternative names

a ⟮network switch⟯ is more rarely also called a ⟮bridging⟯/⟮switching⟯ ⟮hub⟯ or a ⟮MAC bridge⟯