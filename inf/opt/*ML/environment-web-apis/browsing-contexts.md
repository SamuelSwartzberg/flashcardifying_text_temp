
# browsing contexts

A browsing context is the environment in which a browser displays a Document. 
A browsing context may be a tab or a window as well as a frame (iframe/frame)

A browsing context has a corresponding WindowProxy object.
A WindowProxy object wraps the currently-being-viewed Window object.
A WindowProxy objects [[Window]] represents the wrapped window.
the Window WindowProxy is currently wrapping is called the active window, the document associated with that window the active document.
When the browsing context is navigated, the Window wrapped by the WindowProxy object changes.

A browsing context has an opener browsing context, representing the browsing context from which it was opened (subject to noopener etc.)

Certain elements (for example, iframe elements) can instantiate further browsing contexts. These elements are called browsing context containers.
a browsing context container (essentially an iframe) has a nested browsing context
a nested browsing context has a `container` which is its browsing context container.
a nested browsing context's container document, which is its containers node document.


Browsing contexts may relate to each other in a tree w/ parents and children.
A top-level browsing context has no parent browsign context.

Each browsing context has a session history.
A session history is a list of Document objects.
The documents that make up a session history are those that the browsing context has presented, is presenting, or will present. 


It is possible to create new browsing contexts that are related to a top-level browsing context without being nested through an element. Such browsing contexts are called auxiliary browsing contexts. Auxiliary browsing contexts are always top-level browsing contexts.

An auxiliary browsing context has an opener browsing context, which is the browsing context from which the auxiliary browsing context was created, and it has a furthest ancestor browsing context, which is the top-level browsing context of the opener browsing context when the auxiliary browsing context was created.
The opener attribute of Window returns the WindowProxy object of the opener broswing context, if extant/available.

## secure contexts

Things that can only be used in secure contexts: Notifications
A document is in a secure context if it is the active document of a secure top-level browsing context (i.e.a document within a theoretically secure iframe browsing context is not secure if it's top-level browsing context is not also secure)
a resource is secure 