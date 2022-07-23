# window

The Window interface represents a window containing a Document (however, the window is not persistent, but changes during navigation as well. the browsing context is the persistent thing)
A global variable, window, representing the window in which the script is running, is exposed to JavaScript code.
A Window has an associated `Document`.
You can get the document associated with a window by window.document.
The `Document` associated with a window only changes during navigation.
Each Window has an associated `Navigator`.

## bars

the Window object has a few properties representing certain UI elements (all bars), all represented by a BarProp object with the single attribute 'visible'
BarProps: locationbar, personalbar, menubar, crollbars, statusbar, toolbar

## Web Storage API

the Web Storage API is made up of sessionStorage and localStorage.
sessionStorage and localStorage both implement the Storage inteface.
getItem(name)
setItem(name,value)
removeItem(name)
clear()

sessionStorage lasts for a session, localStorage lasts until cleared.
localStorage is larger than sessionStorage.

## notifications

Notification.requestPermission() is a promise, which if fulfilled means we have recieved permission to send notifications.
Browsers increasingly don't even allow us to ask for notification permissione exept in response to user action.
After gaining permission, we can create notifications with the Notification() constructor.
the ⟮Notification() constructor⟯ takes two arguments, the ⟮title of the notification⟯ and an ⟮object of options⟯
the options object for the notification constructor as a bunch of properties that precisely configure the notification.
.close()|closes the notification manually
Notification objects can have the events click, close, error and show (when the notification is shown) triggered on them.

## Intersection Observer API

The Intersection Observer API provides a way to asynchronously observe changes in the intersection of a target element with other elements or the viewport.

## intervals

⟮window⟯.​setTimeout(function, delay, args);

## misc

window.getComputedStyle(‹element›) gets a read-only CSSStyleDeclaration.