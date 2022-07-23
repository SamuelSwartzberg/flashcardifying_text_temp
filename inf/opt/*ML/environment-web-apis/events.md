# events

## EventTarget

The EventTarget interface is implemented by objects that can receive events and may have listeners for them.

## event handler registration

event handler registration can be done via the content and IDL attribute on‹event› or EventTarget.addEventListener()
the on‹event› attribute takes a function to call.
on‹event› doesn't work on non-`Elements`
addEventListener allows for registration of more than one event handler for the same event on the same EventTarget.
on‹event› usage is not recommended, as it will overwrite other event handlers registered on the same element.
event handlers get an `Event` as an argument.

to work, we must pass removeEventListener the event as well as the ⁑exact same function object⁑

## event capturing

in the capturing phase, the browser goes from the root element up to the target downwards
in the target phase, the browser triggers any event handlers on the target itself
in the bubbling phase, the browser goes from the the target up to root element upwardswards
capturing phase › target phase › bubbling phase
capturing/bubbling event handlers trigger during the capturing/bubbling phase respectively, and both on the target phase
Event.bubbles prevents bubbling

## Event

Event.target returns a reference to the thing on which the Event was dispatched.
Event.currentTarget / this returns a reference to the thing on which the Event is being handled.

### defaults

calling Event.preventDefault() or returning false from an on‹event› handler prevents the default
touchstart, touchmove (FF, Chrome, Edge) have passive: true by default
tell the browser that you won't call preventDefault()   3rd option of addEventListener {passive: true}
Event.defaultPrevent|was a default prevented?

## patterns

⟮event delegation⟯ is ⟮handling events⟯ (that are ⟮similar somehow⟯) on ⟮a common ancestor⟯
Event delegation only works due to event bubbling

## node

node handles events in the module `event`, where everything that can have events implements `EventEmitter`.

### EventEmitter methods

on(‹name›, ‹callback›)|add event handler
off/removeListener|remove an event handler
once|add one-time event handler
emit|trigger an event
removeAllListeners|remove all listeners from event emitter