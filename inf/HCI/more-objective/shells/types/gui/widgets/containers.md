
# containers

TODO: definition container
A lightbox is a box/container that displays images/videos by filling the screen and dimming out the rest of the page/UI.

## sidebars

flex-container:⟮h∞;✫440eb7ec02550be3045c969dc02dc7f2.png✫✫162vsE7VWrMgBdBTF8MCKXw.jpeg✫✫ditch-sidebar-2016-2-fox.jpg✫✫ditch-sidebar-2016-4-washington.jpg✫✫sidebars.png✫⟯
A ⟮sidebar⟯ is an UI element that is displayed ⟮to the side of⟯ ⟮the main content⟯ or ⟮of the screen⟯. ⟮hb;Sidebars may be ⟮navigation bars⟯, contain ⟮tools⟯ or contain ⟮further content⟯. ⟮hb;Sidebars are generally ⟮reasonably wide (i.e. not just icons).⟯⟯⟯ 

## drawer

A drawer is a container at one edge that is show-hidable.
A drawer typically takes up most of the screen when opened on a mobile device.
A drawer uses a shadow dims the rest of the UI when expanded, seemingly appearing in front of it.
Often, the menu a hamburger button triggers is a drawer.
drawers on android can typically also be opened with a swiping gesture.

## windows

### windowlets

#### dialog box

A dialog box is a small window that appears in front of the main window due to some event or action and requires some sort of response.
An alert box is a dialog box which contains important information and only accepts the response of ;close'.
A modal dialog box is often just called a modal.
zenity   create GUI (GTK) dialog boxes
dialog   create TUI dialog boxes

The dialog element rerpesents a dialog box container semantically.
The dialog element has a boolean attribute open representing whether the dialog should be shown or not.
‹form› elements can close a dialog if they have the attribute method="dialog". When such a form is submitted, the dialog closes with its returnValue property set to the value of the button that was used to submit the form.

#### tooltips ＆ popovers

flex-container:⟮h∞;✫sm_13gJ2VKho0yW4vEovAMtrjg.jpg✫⟯⟮ha;✫sm_220px-Mobile_URL_tooltip.png✫⟯]]][[[⟮ha;✫sm_1sGOKl17J48qhDRMx-foqOw.gif✫⟯⟮ha;✫sm_2021-06-24--02-37-46-screenshot.png✫⟯
⟮Tooltips⟯ and ⟮popovers⟯ are similar in that ⟮they both appear close to the thing that triggered them⟯. 
A ⟮tooltip⟯ is an element/component ⟮with extra text⟯ which ⟮appears⟯ when ⟮when hovering over something⟯ 
A ⟮popover⟯ is a element/component that usually ⟮appears⟯ when ⟮interacting with something⟯ ⟮directly adjacent to that thing⟯. it ⟮is a modal (creates a mode⟯). 
⟮Popper⟯ is a ⟮JS⟯ library for ⟮tooltips⟯/⟮popovers⟯. 


# disclosure widgets

A disclosure widget has a collapsed state where it only shows a heading, and an expanded state which shows the heading and more content contained within.
With a disclosure widget, the content contained within is shown if the heading is interacted with.
With a disclosure widget, the heading often indicates that it can be expanded/shrunken either via ▼/▲ or via +/-
In html, a disclosure widget is defined via a details element.
In html, the header of a disclosure widget is defined by a summary element.
An accordion is a set of multiple disclosure widgets.
Most commonly, disclosure widgets start out in their collapsed state by default.
In html, you can force a disclosure widget to start in its open state by specifying the boolean attribute open.
flex-container:✫disc.png✫✫kfw-disclosure.jpg✫⟮h2;✫sm_FAQ-Content-Style-Accordion.gif✫⟯
