
# memory 

Memory allocation is setting aside memory for a purpose, e.g. to store entities of a programming language.
Memory deallocation is releasing previously allocated memory.

## The stack and the heap

The call stack is often only called the stack.
The call stack implements the stack ADT
The call stack is made up of stack frames.
The stack frame usually includes at least ⟮the arguments⟯, the ⟮return address⟯, and ⟮local variables⟯.
When we call a callable unit, a new stack frame is pushed on the stack, and the stack pointer is updated.
When we return from a callable unit, the stack frame at the top of the stack is popped, and the stack pointer is updated.
The stack frame at the top of the stack is the stack frame of the currently executing callable unit.
The stack pointer points at the most recently referenced location on the stack.
The memory address at which the stack starts out when it is size 0 is the stack origin.
If the stack has size 0, the stack pointer is (or better be :P) at the stack origin.
The stack may grow upwards = larger memory addresses or downwards = smaller memory addresses (however this needs to be fixed in advanced)
stack grows upwards|stack overflow|address › stack_origin_addr+ max_stack_size
stack grows upwards|stack underflow|address ‹ stack_origin_addr
stack grows downwards|stack overflow|address ‹ stack_origin_addr-max_stack_size
stack grows downwards|stack underflow|address › stack_origin_addr
Since each call to a callable unit adds a stack frame, infinite recursion causes a stack overflow (unless the compiler optimizes the recursion away)
The stack is significantly faster than the heap, since it's implementation is far simpler.
The heap can become fragmented.
The heap is managed much less strictly than the stack.

In general, there is one stack per thread and one heap per process (instance of a program)


## stack trace

A stack trace is a report of the active stack frames during the execution of a program.
Stack traces are often automatically printed in the case of unrecoverable errors
to show a stack trace on error in rust, set the env variable `RUST_BACKTRACE=1`

## static and dynamic as size

static types/statically sized types (!= static variables) have a size that can be known at compile time.
dynamic types/dynamically sized types have a size that cannot be known at compile time. 
One of the main cases for static arrays is that they are static(ally sized) types.
Only statically sized types can be stored on the stack (= in automatic variables).
Dynamically sized types are stored on the heap. 
To store dynamically sized types on the stack, one typically has a pointer.
Most record types are dynamically sized types.
In rust, statically sized types implement `Sized`, dynamically sized types implement `?Sized`
In rust, pointers to dynamically sized types are fat pointers.
In rust, the most common dynamically sized types are trait objects and slices.
Pointers to slices are fat pointers because they also store a length of the slice.
trait objects are fat pointers because they also store a virtual method table.

## static, automatic and dynamic variables

The lifetime of a variable is the time where it is in a valid state, which generally coincides with when it has memory.
The lifetime of a value is the time where it occupies a certain region of memory.
The lifetime of a variable cannot outlive the the lifetime of its value.

A static variable is allocated for the entire lifetime of the program.
Static variables fall outside of the clear stack heap distincition, as they are stored in a data segment.
A data segment is a part of the object file (file of object code = compiler output, see compilers) that contains static variables.
The read-only data segment is the part of the data segment (or an extra data segment) that contains read-only static variables (ergo static consonants)
the read-only data segment may be called rodata.

### automatic and dynamic variables

The terms automatic and dynamic variables/memory allocation are mainly used in C-style languages.

An automatic variable is a variable that has its memory allocated and deallocated automatically when the program enters and leaves the variables scope.
Automatic variables have a lifetime of the variables scope.
In general, automatic variables genrally must be statically sized.
Any automatic variable can go out of scope.

Dynamic memory allocation creates lifetimes of your choosing: their memory is allocated and deallocated by you or a memory management system.
(dynamic variable isn't a real term, I've introduced it here for terminological parallelism)
Def: Automatic/static variables use automatic/static memory allocation.

Use-after-free is a vulnerability where memory is used after it has been deallocated.
Use-after-free can generally only occur to dynamically allocated memory.

### lexical and nonlexical lifetimes

In lexical lifetimes, the lifetime of a value is until the end of its lexical scope
In non-lexical lifetimes, the lifetime of a value is until it is last used within its lexical scope.
In general, the difference between lexical and non-lexical lifetimes does not matter, however if the value is a reference Rust's borrow checker cares about if you're holding on to it. Hence, rust implements non-lexical lifetimes for references.

lifetime-annotation ::= '‹name›
lifetime-annotations specify named lifetimes
You must specify all lifetimes you are gonna use as type parameters.
In rust, in theory all references used in callable units require a lifetime annotation, though in most cases it can be left out due to lifetime elision.
lifetime annotations cannot be elided in cases where the compiler cannot figure out how parameters and return value relate.
ergo, lifetimes cannot be elided if the function returns a reference, the function takes more than one reference as a input parameter, and the function is not a method.
Importantly, lifetime annotations beside 'static do not change lifetimes, merely indicate how lifetimes of references relate (specifically, "treat all these lifetimes as the lifetime of the shortest one")
Rust indicated static variables with a 'static lifetime annotation

## memory management

Memory management is managing the memory of an application.
One of the main jobs of memory management is memory allocation and deallocation.
Memory management may be manual = performed by the programmer or automatic = performed by the programming language automatically.
Dynamic memory allocation can be handled by manual memory management or by automatic memory management.
Automatic variables are handled by automatic memory management.
static variables are not subject to memory management.
Most higher-level programming languages have no manual memory management at all.

A destructor is a method which is envoked just before the memory of a thing is released.


### types of data

Garbage data is data that cannot be used anymore (e.g. reference out of scope)
The opposite of garbage data is live data.
Outside of programming, garbage data is sometimes used for data that is unusable in some way (e.g. corrputed, garbled)

### manual memory management

In C, dynamic memory allocation is done by manual memory allocation.
malloc() allocates the specified number of bytes
calloc() allocates the specified number of bytes, and sets them to 0
free() releases teh specified block of memory back to the system.

### automatic memory management

The three most common types of automatic memory management are garbage collection, automatic reference counting, and RAII.

#### garbage collection

Garbage collection is a form of automatic memory management in which a garbage collector deallocates garbage memory.

#### reference counting

(manual) reference counting is a form of manual memory management
automatic reference counting is a form of automatic memory management
In reference counting, when no more references to a certain value exist, then it is destroyed
In reference counting, a value (most commonly an object) as some kind of field indicating how many references to it exists.
In manual reference counting, we call increment and decrement methods to indicate how many references there are.
In automatic reference counting, increment/decrement methods for refrences are called automatically. 
Circular set of references are called reference circles.
reference circles can allow things in refrence counting to never reach reference count 0 and thus be destroyed.

In rust, reference counting is implemented by Rc‹T›.
Rc‹T› allows multiple owners, where each call to clone() increases the reference count.
In rusts implementation of reference counting, dropping Rc‹T› decreases the reference count.

#### RAII

RAII = resource acquisition is initialization
In RAII, memory for a value is allocated by its constructor and deallocated by its destructor.
In rust, the destructor for RAII is drop() of the Drop Trait.
In rust, when a variable goes out of scope, the value it owns is dropped.
