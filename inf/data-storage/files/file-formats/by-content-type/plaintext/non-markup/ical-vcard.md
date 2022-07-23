# ICAL/VCARD

ical|text/calendar|calendar information|RFC 5545|.ics
vcard|text/vcard|contact information|RFC 6350|.vcf
The iCalendar object is organized into individual lines of text, called content lines. 
Any content lines not acting as delimiters are called properties.
Rough general ENBF:
ical, vcard ::= {‹contentline›}
contentline ::= ‹name›{;‹param›}:‹value›‹CRLF›
name ::= ‹iana-token›|‹x-name›
param ::= ‹param-name›=‹param-value›{,‹param-value›}

The iana-tokens "BEGIN" and "END" signify the beginning and end of an icalendar or vcard object, or a component/subcomponent in the case of Ical.
There is currently only one subcomponent, VALARM
BEGIN and END take a value of VCALENDAR for an ical object and VCARD for an vcard object

ical-object ::= ‹ical-begin-line›‹version-line›‹prodid-line›{‹ical-component›}‹ical-end-line›
ical-begin-line ::= BEGIN:VCALENDAR‹CRLF›
ical-end-line ::= END:VCALENDAR‹CRLF›
version-line ::= VERSION:2.0‹CRLF›
prodid-line ::= PRODID:‹string›‹CRLF› # UID of creator
ical-component ::= ‹begin-line›{‹contentline›|‹ical-component›}‹end-line›
begin-line ::= BEGIN:‹component-name›‹CRLF›
end-line ::= END:‹component-name›‹CRLF›

In vCard, properties are direct children of the ⟮the vCard object⟯
In general, an .ics contains one ical object, however a .vcf may contain multiple ical objects

vcard-object ::= ‹ical-begin-line›‹version-line›{‹contentline›}‹ical-end-line› # no prodid
cal-begin-line ::= BEGIN:VCARD‹CRLF›
ical-end-line ::= END:VCARD‹CRLF›
version-line ::= VERSION:4.0‹CRLF›

icalendar lines may be a maximum of 75 octets long. If they are longer, they are broken up into multiple lines, where a leading space/tab on the new line indicates it is a continuation.

ical/vcard property names
ATTENDEE   the users attending/assigned a task
DTEND   end time
DTSTART   start time
ORGANIZER   the organizer of the event
RRULE   rules for repeating
SUMMARY   title/summary
VALARM   Alarm/Reminder
VEVENT   Event
VFREEBUSY   free/busy time
VJOURNAL   Journal entry
VTIMEZONE   timezone definition
VTODO   Task/Todo