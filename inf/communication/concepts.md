
# concepts

A telegraph is a system for communicating at a distiance via coded signals
semaphore is telegraphy via visual signalling.
master/slave is (problematically) when one entity controls or serves as an example to other entity(s)
Crosstalk is a signal transmitted on a channel causing an undesired effect on another circuit or channel

## serial and parallel

Serial communication sends its information one after another over the channel.
Parallel communication sends multiple piecies of information simultaneously over multiple subchannels.
One would expect parallel communication to be faster than serial communication, with the factor equivalent to the amount of channels/wires/whatever, however serial communication can often be clocked far higher to make up for it.
Serial communication is often far easier/simpler to implement and thus less error-prone, cheaper and thinner/lighter than parallel communication.

## allow ＆ deny

an allowlist implies forbidding everything by default
an allowlist enumerates a set of things that may pass
a denylist implies allowing everything by default
an denylist enumerates a set of things that may not pass
allowlists were/are known as whitelists
denylists were/are known as blacklists

## pushpullpoll

pulling is where the request initiates from the client, and is responded to by the server
pushing is where a request is initiated by a server.
polling is frequently checking whether a thing is in a certain state
polling may be used to simulate push protocols.

## state

### sessions

In computer science, a ⟮session⟯ is ⟮started at some point⟯, ⟮ends at some point⟯, and during this time ⟮maintaines state⟯.
A browser session starts when the browser is opened and ends when the browser is closed (unless session restoring is used.)
A login session starts when a user logs in and ends when a user logs out or the existence of the session is otherwise terminated.

## proxy

flex-container:✫Proxy_concept_en.svg✫

A ⟮proxy (server)⟯ is a ⟮server/server application⟯ that ⟮acts as an intermediary between⟯ ⟮a client requesting a resource⟯ and ⟮the server providing that resource.⟯
A reverse proxy is a proxy that appears to clients to be an ordinary server, but forwards requests to other servers in the background.
flex-container:✫Reverse_proxy_h2g2bob.svg✫

Reverse proxies are sometimes called surrogates or gateways.

## directions

simplex|one direction only
duplex|bidirectional
half duplex|bidirectional, but only one at a time
full duplex|bidirectional, both simultaneously

## fresh and stale

In technical contexts, ⟮fresh⟯ and ⟮stale⟯ are often contrasted. 
In technical contexts, something ⟮fresh⟯ is ⟮still relevant/valid/useful⟯. 
In technical contexts, something ⟮stale⟯ is ⟮no longer relevant/valid/useful⟯. 

# design

The ⟮robustness principle⟯ is "⟮be conservative in what you send⟯, and ⟮liberal in what you accept⟯".
The robustness principle is often said to be ⟮good design⟯, but also ⟮create bad de-facto standards⟯

# interfaces 

At its most general interface is a shared boundary across which information flows.
An interface specifies specific channels (endpoints, methods, ...) for the access of information.

## IDL 

interface description/definition language =short=> IDL
An IDL is a language to define an interface in a language-independent way.

## API

API = application programming interface
An API is an interface of a piece of software/module/web service/etc.
the point where one interfaces with an API is an endpoint
Glue code is code that is needed to make two things (mostly interfaces) which are not interoperable interoperable.
A wrapper library is a library that contains one or more other libraries and transforms their interface into a different interface.
wrapper libraries may be glue code, but also may be for abstraction or to improve a mediocre interface.
API bindings are glue code to allow one to call a specific API.
API bindings for libraries are generally wrapper libraries.
A foreign function interface allows one to call functions of a different language from ones given language.
A foreign function interface often calls C or C++ functions (due to their ubiquity).
To use a foreign function using a foreign function interface often requires you to write some glue code (e.g. the signatures), though most of the glue code is handled by the language itself.
ffis may be glue code. 
One could write one's own API bindings or a wrapper library using a foreign function interface.
A shim is a library that takes API calls for something else and then does something with them.
A shim may do one or more of with a given call: redirect it, change the arguments, handle it itself.
A polyfill is a shim for a browser API, which passes it through if available, and implements it itself if not.

# protocols

A protocol is a set of rules that allows transmitting messages via a medium.
Protocols are often layered to produce a protocol stack.
While the medium over which a message may be transferred for a protocol may be an actual medium, in protocol stacks the medium is merely a lower protocol.
In protocol stacks, the only truly physical medium is the lowest layer.
A message in any protocol typically consists of some headers/metadata and a payload.
A protocol data unit is the fundamental unit a protocol transmits, i.e. its message.
If a protocol is acting as a medium for a higher layer in a protocol stack, a service data unit is the payload of the protocol data unit of the current protocol, which IS the protocol data unit of the higher layer.

Protocols that are transferred over wires as a medium typically also define the characteristics of these wires and the eletrical connectors connecting them.

PDU = Protocol data unit
SDU = Service data unit

