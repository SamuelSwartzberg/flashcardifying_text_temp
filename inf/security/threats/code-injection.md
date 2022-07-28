# code injection

Code injection is an attack where malicious code is injected due to some flaw.

## attack gateway

### user input

user input code injection is code injection via user input.

## attack mechanism

### delimiter/terminator

Delimiter/terminator-based code injection uses delimiters/terminators to escape from  another mode of interpretation to code interpretation.

#### string

string delimiter/terminator-based code injection is delimiter/terminator-based code injection via string delimiters.
Null-byte injection is string delimiter/terminator-based code injection when dealing with null-terminated strings.

### buffer size

Buffer overflow is when a buffer of a specific size is written to with data larger than that buffer, thus writing to a different memory location.
buffer overflow code injection is code injection via intentional buffer overflow, with executable code in the overflown part (ergo a code injection attack), which may then be executed as normal code.