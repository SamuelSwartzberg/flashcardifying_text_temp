# layer 7

HTTP, SMTP, POP, SSH, telnet...

## common concepts

### URLS ＆ Hyperlinks

#### URI

IRI   Internationalized Resource Identifier
URI   Uniform Resource Identifier
URN|Uniform Resource Name
URLs generally locate things on the internet, generally on the application layer.
URIs used to be subdivided into URLs and URNs.
Mainly historically, URLs were for locating things, and URNs were unique identifiers of a resource.
Today, URNs are merely another scheme of URIs, urn:
URL and URI are often used synoynously even in expert circles, even RFCs disagree.
URI can only use an ASCII-subsset.
Within URIs ASCII subset, there is a distinction between reserved and unreserved characters.
URI unreserved characters: ⟮alphanumerical⟯, ⟮-⟯, ⟮_⟯, ⟮.⟯, ⟮~⟯ (the rest are reserved)
IRIs are a superset of URIs that also allow for non-ASCII characters.

In URLs, Reserved characters and characters outside of the URL character set need to be URL/percent-encoded

uri ::= ‹scheme›:[//‹authority›/]‹path›[?‹query›][#‹fragment›]
host ::= ‹ipv4-address›|‹ipv6-address›|‹FQDN›
authority ::= [‹userinfo›@]‹host›[:‹port›]
userinfo ::= ‹username›[:‹password›]
query ::= ‹key›=‹value›{‹query-delimiter›‹key›=‹value›}
query-delimiter ::= ＆|;

The password part of the userinfo component of an URI is deprecated (password inplaintext)
For HTML, the fragment of an URI is often an ID

URI schemes are generally the same as the application-level protocols they refer to, though there are schemes that do not correspond to protocols.
file is a scheme that is not a protocol, it allows accessing local files.
Most browsers have a scheme to navigate their own internal admin pages.
apt|installing apt packages
browsername|scheme for whatever browser-internal pages
tel|phone numbers
mailto|email messages

mailto-url ::= mailto:[‹email-address›{,‹email-address›}][?‹email-key›=‹value-percent-encoded›{＆‹email-key›=‹value-percent-encoded›}]
email-key ::= subject | cc | body | ...

#### URN 

the path of URN URIs can theoretically be anything, however it typically has the following syntax
urn-path ::= ‹urn-namespace›:{‹urn-subnamespace›:}‹unique-id› 
urn-namespace ::= ISBN|ISSN|UUID|...
e.g. urn:oasis:names:specification:docbook:dtd:xml:4.1.2

#### origins

The group of scheme/host/port making up a web resources origin are sometimes called the (scheme/host/port) tuple
in a scheme, host, port tuple, host is actually the FQDN
a web resources ⟮origin⟯ is defined by its ⟮scheme/protocol⟯, ⟮FQDN(often inaccurately just called host)⟯, and ⟮port⟯ tuple
Two or more URLs that share a common origin (s/h/p tuple) are same-origin, all others are cross-origin
The ⟮same-origin⟯ policy allows ⟮same-origin⟯ access by ⟮default⟯, and ⟮provides predefined channels and restrictions⟯ for ⟮cross-origin⟯ access
The ⟮same-origin⟯ policy is relevant only when ⟮two pages want to communicate⟯
The same-origin policy is ⟮active⟯ (⟮in some shape or form⟯) in ⟮all modern browsers⟯

#### domains

A domain consists of n labels separated by dots.
The further right a label is in a domain name, the higher it is in the hierarchy.
FQDN = fully qualified domain name
PQDN = partially qualified domain name
TLD = top-level domain
The FQDN is the domain including all labels.
The PQDN is a domain which only includes a part of the FQDN.
The rightmost label of a FQDN is the TLD.
the second-rightmost label of a FQDN is a second-level domain.

A host is a device connected to a computer network.
In technically correct usage, the leaf of a given FQDN is the hostname.
hostname comes from it being the name of the host, a device connected to a network.
frustratingly hostname is often also used as a synojym for PQDN or FQDN
Domains to the left of a domain label are subdomains of that label.
Domain is a very ambiguous term: It may refer to everything but the hostname, any PQDN, or the FQDN.
a public suffix is a domain under which one can or at one point could register a domain name.
examples: .co.uk, .com, .tech
Many public suffixes are TLDs, but e.g. .co.uk is a public suffix but not a TLD, while some country codes are TLDs but not public suffixes (since authorities of some country code TLDs (e.g argentinia in the past) only allow registrations on subdomains such as .com.ar)
A registrable domain name consists of a single label plus a public suffix.
A registrable domain name is so called because it is or at one point would have been registrable

In the past, the www hostname was popular, since webservers might have had many different application-level services and thus there was a desire to enforce separation between them.

##### linux hostnames

Linux has three hostnames, static, transient, and pretty.
The pretty hostname can be pretty much anything
The static hostname is used for programmatic purposes, the transient hostname is used as a fallback.
While the pretty hostname can be pretty much anything, static and transient hostname are limited to 64 characters.

the `hostname` command shows the hostname, which is the same for DNS, NIS and YP.

#### hotlinks, deeplinks

hotlinking = inline linking
Hotlinking is embedding a resource from ⟮another fqdn⟯
A deep link may be a link that links to any other page than the site's home page, a link that links to content within an installed app instead of a webpage (polysemy).
A link to the homepage of a page is called a surface link

### URL manipulation libraries/objects

`URL`|JS

The ⟮URL⟯ constructor takes ⟮a string of the url⟯, and optionally ⟮a base url⟯ (if the url is ⟮relative⟯)

## applications

### cURL

⟮cURL⟯ is a project for ⟮transferring data⟯ using various ⟮application protocols⟯. 
one half of ⟮cURL⟯ is ⟮the command-line tool⟯ ⟮curl⟯. 
the other half of ⟮cURL⟯ is ⟮the library libcurl⟯ with ⟮bindings for most major programming languages⟯. 
curl syntax: ⟮curl⟯ ⟮[options]⟯ ⟮{URLs⟯} 

⟮c+;s16;-i⟯ and ⟮c+;s15;--include⟯ ⟮show HTTP response headers⟯ 
To ⟮set custom headers⟯ in curl, use ⟮c+;s20;-H⟯/⟮c+;s19;--header⟯ ⟮"My-Header: My value"⟯ 
To ⟮set the query string⟯ to a certain value in curl, use ⟮c+;s44;-d⟯ OR ⟮c+;s23;--data⟯ ⟮c+;'key=value＆key2=value2'⟯ 
To ⟮simulate a filled in form⟯ with curl, use ⟮c+;s45;-f⟯ or ⟮c+;s26;--form⟯ ⟮"key=value"⟯ (supports ⟮more fancy syntax for files etc.⟯ )  
To make curl ⟮fail on error⟯, use ⟮c+;s31;-f⟯ or ⟮c+;s30;--fail⟯ 
To ⟮make a HTTP HEAD request (instead of the default GET⟯) with curl, use ⟮c+;s34;-I⟯ or ⟮c+;s33;--head⟯. 

To ⟮make curl follow redirects (e.g. 301 Moved Permanently⟯), use ⟮c+;s37;-L⟯ or ⟮c+;s36;--location⟯ 
If ⟮you've specified -L/--location⟯ for curl, ⟮--max-redirs⟯ sets ⟮how many redirects you want to follow⟯. ⟮-1⟯ means ⟮infinite redirects⟯ 

There are bunch of sites ⟮designed to be `curl`ed⟯ to do something useful. 

Site|Does what when `curl`ed?
⟮wttr.in⟯|⟮get weather⟯


### various data-fetching CLIs

#### youtube-dl

⟮youtube-dl⟯ is a ⟮CLI⟯ tool for ⟮downloading from⟯ ⟮mainly⟯ ⟮youtube⟯, ⟮but also from other platforms⟯. 
basic syntax for youtube-dl: `⟮youtube-dl⟯ ⟮[OPTIONS]⟯ ⟮URL {URL⟯}` 


youtube-dl: ⟮don't actually download the video, just preview⟯, so to speak: ⟮-s/--simulate⟯ 

There is ⟮a set of options⟯ for ⟮youtube-dl⟯ that ⟮start with --get-⟯ and ⟮only return the requested information (e.g. id, format, filename, title, duration, etc.⟯) 
^--get-format, --get-title, etc.

The ⟮--format / -f FORMAT⟯ option of youtube-dl is for s⟮electing the format you want to download the thing in⟯. 
You can ⟮list available formats for --format⟯ with ⟮--list-formats/-F⟯ 


--format accepts a sophisticated syntax as an argument: (it's actually slightly more complicated, but I've simplified a little)
```
Format specifier syntax: ⟮--format⟯ ⟮‹format-specifier›⟯⟮{,‹format-specifier›⟯}  # for ⟮downloading mutliple formats at once⟯
⟮format-specifier⟯: ⟮‹single-format›⟯⟮{/‹single-format›⟯} # for ⟮relative precedence of multiple formats, depending on what's available⟯
⟮single-format⟯: ⟮‹single-format-selector›[+‹single-format-selector›]⟯ # if ⟮two are specified⟯, ⟮the first one is for video and the second is for audio⟯
⟮single-format-selector⟯: ⟮[‹general-quality›]⟯⟮{\[‹property›‹operator›‹value›\]⟯}
⟮general-quality⟯: ⟮‹file-extension›|‹quality-keyword›⟯
⟮file-extension⟯: # will ⟮get the best format⟯ of ⟮the given file extension, e.g. mp3⟯
⟮quality-keyword⟯: ⟮best|worst|bestvideo|worstvideo|bestaudio|worstaudio::contains |⟯
⟮property⟯: # things such as ⟮filesize, width, height, tbr (total average bitrate), fps, ...⟯
⟮operator⟯: # things such as ⟮c+;=, !=, ›.... as well as ^=, $=, *= etc.⟯
```


The ⟮c+;s46;-x⟯/⟮c+;s45;--extract-audio⟯ option makes ⟮youtube-dl extract the audio into its own file⟯. 
If ⟮using -x/--extract-audio⟯, you ⟮can specify the format⟯ ⟮with --audio-format FORMAT⟯, which ⟮accepts the subset of things for --format FORMAT⟯ that ⟮make sense for audio⟯. 


## protocols

### WHOIS

whois is the command to query WHOIS.

### SMTP, IMAP, POP

SMTP = Simple Mail Transfer Protocol
IMAP = Internet Message Access Protocol
POP = Post Office Protocol

SMTP is used by mail servers for sending and recieving email, and by mail clients typically only for sending messages
IMAP or POP3 are both used to retrieve email messages (though they can be used for other things)
IMAP keeps messages on the server while POP3 deletes them (by default)
Between IMAP and POP3, IMAP is more feature-rich.

### HTTP

HTTP|HyperText Transfer Protocol

⟮HTTPS⟯ is an ⟮encrypted⟯ version of ⟮HTTP⟯
A ⟮mixed content⟯ page is a ⟮HTTPS⟯ page that ⟮also includes content fetched over HTTP⟯

When you navigate to a new URL, the browser sends an HTTP request
The client sendds a HTTP request, and the server returns an HTTP response.
http-request-message ::= ‹http-request-header-part›‹CRLF›[‹http-request-body›]
http-request-header-part ::= ‹http-request-line›{‹http-request-header›}
http-request-line ::= ‹request-verb› ‹path› ‹HTTP-version›‹CRLF›
http-request-header ::= ‹key›: ‹value›‹CRLF›
HTTP/2 did not change the HTTP semantics, merely stuff under the hood.

in HTTP/1.1, in a request, besides the request line, a host header is necessary
HTTP request verbs are case-sensitive
If a form is submitted via POST, the query string ends up in the body of the request message
If a form is submitted via GET, the query string ends up in the request url as the query element
When you make a GET request to a directory, e.g. `/directory/`, it will return `/directory/index.html`, if extant, or possibly the directory listing if enabled, otherwise 404

http-respose-message ::= ‹http-response-header-part›‹CRLF›[‹http-response-body›]
http-response-header-part ::= ‹http-status-line›{‹http-response-header›}
http-response-line ::= ‹CRLF›
http-reponse-header ::= ‹key›: ‹value›‹CRLF›

#### request verbs

TRACE   Ask the server to return a diagnostic trace
PUT   Ask the server to store the data
POST   Post data up on the web server
OPTIONS   Ask the server to return the list of request methods it supports
HEAD   Get the header that a GET request would have gotten
GET   Get a resource from the server
DELETE   Ask the server to delete the data
CONNECT   Tell a proxy to connect to another host and simply reply the content

#### status codes

⟮Status-Code⟯|⟮Reason-Phrase⟯|Further explanation
⟮1xx⟯|⟮Informational⟯
⟮100⟯|⟮Continue⟯|⟮The server is working on it, dammit!⟯
⟮2xx⟯|⟮Success⟯
⟮200⟯|⟮OK⟯|⟮The request is fulfilled.⟯
⟮3xx⟯|⟮Redirection⟯
⟮301⟯|⟮Move Permanently⟯|⟮The resource has moved permanently.⟯
⟮302⟯|⟮Move Temporarily⟯|⟮The resource has moved temporarily.⟯
⟮304⟯|⟮Not Modified⟯|⟮The resource has not been modified⟯
⟮4xx⟯|⟮Client Error⟯
⟮400⟯|⟮Bad request⟯|⟮The server could not understand the request⟯
⟮401⟯|⟮Authentication Required⟯|⟮Requires Username/Password⟯
⟮403⟯|⟮Forbidden⟯|⟮Server refuses to supply the resource, regardless of identity of client⟯
⟮404⟯|⟮Not Found⟯|⟮The requested resource cannot be found in the server⟯
⟮405⟯|⟮Method Not Allowed⟯|⟮The method used (e.g. POST) is a valid method, but the server does not allow that method for the resource requested⟯
⟮451⟯|⟮Unavailable For Legal Reasons (refrence to ray bradburry)⟯
⟮5xx⟯|⟮Server Error⟯
⟮500⟯|⟮Internal Server Error⟯|⟮Server is confused⟯
⟮501⟯|⟮Method not Implemented⟯|⟮The method name is invalid (e.g. Get instead of GET⟯)
⟮502⟯|⟮Bad Gateway⟯|⟮Proxy recieved bad response from upstream server⟯
⟮503⟯|⟮Service Unavailable⟯|⟮Server cannot respond due to overloading or maintenance⟯
⟮504⟯|⟮Gateway timeout⟯|⟮Proxy/Gateway recieved a timeout from an upstream server (gateway seems to be a bit of a misnomer here, or at least it doesn't refer to a router but justt is a synonym for proxy⟯)


#### cache

A ⟮cache⟯ is a thing that ⟮stores data⟯ so that ⟮future requests for that data⟯ ⟮can be served more quickly⟯. 
With ⟮caching and esp. with HTTP caching⟯, the guiding principle is that you want to ⟮store the thing as long as possible⟯, but ⟮update it as soon as it changes⟯. 

A ⟮web cache⟯ AKA ⟮s16;⟮HTTP cache⟯⟯ is ⟮a cache for HTTP requests⟯. 
⟮web/HTTP caches⟯ can either be ⟮shared⟯ or ⟮local/private⟯. 
a ⟮shared⟯ ⟮HTTP cache⟯ sits ⟮somewhere in the internet⟯ and ⟮has many users⟯. 
a ⟮local/private⟯ ⟮HTTP cache⟯ sits ⟮in your web browser⟯ and ⟮is only used by you⟯. 
⟮Any HTTP request⟯ will ⟮first be routed through⟯ ⟮your browser cache⟯ and perhaps ⟮a few network caches⟯ to see if ⟮there is a fresh copy of the response available⟯. 

The main mechanism ⟮HTTP caching⟯ uses is ⟮the Cache-Control header⟯. 
In the days of ⟮HTTP 1.0⟯, the ⟮Pragma header⟯ was used for ⟮caching⟯. 
The ⟮Cache-Control header⟯ is sent ⟮by the server⟯ and specifies ⟮if a resource can be cached⟯, ⟮who can cache it⟯, and ⟮how long it can be cached⟯. 
The ⟮Cache-Control header::caching⟯ consists of ⟮a comma-separated list⟯, with either ⟮boolean keywords⟯ or ⟮key=value pairs⟯ ⟮h∞;(cookie e.g. has a ; separated list) ⟯. 
To specify ⟮how long⟯ ⟮a cache entry⟯ is ⟮fresh (when it becomes stale⟯), one can either specify ⟮max-age=value⟯ as ⟮part of the Cache-Control header⟯ or ⟮the separate Expires header⟯. 
⟮Maximum value⟯ for ⟮Cache-Control:⟯ ⟮max-age⟯ is ⟮1 year⟯ 


Keywords for Cache-Control for if to/who can cache a resource

⟮public⟯|⟮Cache anything, even things that are not normally cached (weird HTTP status codes etc.⟯)
⟮private⟯|⟮Don't cache in shared cache, only in private cache (e.g. browser⟯)
⟮no-cache⟯|⟮Check with the server for change with each request (but don't redownload if unchanged⟯)
⟮no-store⟯|⟮Do not cache the resource in any way⟯


an ⟮ETag⟯ is a mechanism for ⟮judging whether a resouce has changed⟯. 
An ⟮ETag⟯ is ⟮a fingerprint⟯ for ⟮a specific version⟯ of ⟮a file⟯. 
An ⟮ETag⟯ is ⟮opaque⟯ to ⟮the client⟯ but ⟮transparent⟯ to ⟮the server⟯ 
For ⟮ETags⟯, the ⟮server⟯ needs to decide on ⟮a fingerprinting algorithm⟯ that ⟮takes into account⟯ ⟮the file and the version⟯ and ⟮outputs⟯ ⟮a fingerprint⟯. 
The ⟮ETag fingerprint⟯ is sent along by ⟮the server⟯ as ⟮a part of the response⟯ in ⟮an ETag header⟯. 
If we're using ⟮ETags⟯ and ⟮a resource expires⟯, the ⟮client⟯ sends along the ⟮ETag⟯ ⟮fingerprint⟯ in ⟮a If-None-Match header⟯. The ⟮server⟯ uses this to check whether ⟮the fingerprint⟯ still ⟮corresponds to the current version of the file⟯, and returns ⟮304 Not Modified⟯ if ⟮true⟯, or ⟮else⟯ a ⟮normal 200 OK response⟯. 

There's no ⟮built-in/non-hacky way⟯ in ⟮HTTP⟯ to ⟮notify a client that a resource has expired⟯ if they don't ask for it. 
⟮Cache busting⟯ AKA ⟮s89;⟮revving⟯⟯ is a '⟮hack⟯' to ⟮force browsers to redownload new resources⟯ even if ⟮they are not expired.⟯ 
⟮Cache busting⟯ sets ⟮the longest possible max-age⟯ on resources, and if ⟮there are changes⟯, it ⟮renames the file in some way (e.g. a hash suffix⟯), which ⟮forces the browser to redownload⟯. 
⟮Cache busting⟯ is generally done by ⟮build tools such as Webpack automatically⟯ 

flex-container:✫sm_tmpyvxwccqz.png✫



##### cookies

By default, HTTP is stateless, ergo technologies such as cookies exist to enable state.

⟮Cookies⟯ are a concept within ⟮HTTP⟯. 
⟮Cookies⟯ allow ⟮the server⟯ to ⟮keep track of state⟯ in ⟮HTTP⟯, which is itself essentially ⟮stateless⟯. 
⟮Cookies⟯ are usually ⟮first set⟯ by ⟮the server⟯. 
The ⟮server⟯ ⟮sets the cookies⟯ via the ⟮`Set-Cookie`⟯ ⟮HTTP Header.⟯ 
The ⟮browser⟯ ⟮sends⟯ ⟮all relevant cookies⟯ ⟮back to the server⟯ ⟮on each request⟯. 
Syntax of the ⟮`Set-Cookie` HTTP Header⟯: `⟮Set-Cookie⟯: ⟮‹cookiekey›=‹cookievalue›⟯⟮c+;{;⟯ ⟮‹cookiepropertykey›[=‹valuepropertykey›]⟯⟮} ⟯` 
The ⟮`Set-Cookie` HTTP Header⟯ typically contains ⟮one cookie⟯ and ⟮its properties⟯, to ⟮set multiple cookies⟯ ⟮set multiple headers⟯ (there is also a way of ⟮separating them with commas⟯, but ⟮this is nonstandard and often does not work⟯) 
The browser ⟮sends cookies back on request⟯ via ⟮the `Cookie` HTTP header⟯. 
The syntax of the `⟮Cookie⟯` header: `⟮Cookie:⟯ ⟮‹cookiekey›=‹cookievalue›⟯⟮c+;{;⟯ ⟮‹cookie2key›=‹cookie2value›⟯⟮} ⟯` 
Since ⟮cookies are sent back on each request⟯ and since ⟮there are spec-defined size constraints⟯, ⟮the things sent in cookies⟯ are usually ⟮quite small, often only a UID⟯. 

⟮Session cookies⟯ are cookies that ⟮only last until the browser is closed⟯, allthough ⟮they can often be restored by the browser via session restoring⟯. 
⟮Cookies⟯ without an ⟮Expires⟯ or ⟮Max-Age⟯ attribute are ⟮session cookies⟯. 
⟮Persistent cookies⟯ are ⟮cookies that last for a specific time⟯. 
⟮Cookies⟯ with an ⟮Expires⟯ or ⟮Max-Age⟯ attribute are ⟮persistent cookies⟯. 

Due to the ⟮cookie spec⟯, one can usually rely on ⟮cookies⟯ being able to hold at least ~⟮4kb⟯ and at least ⟮50⟯ ⟮cookies per domain⟯, though ⟮often the real limits are far higher⟯ 

Since ⟮persistent cookies⟯ are ⟮deleted⟯ ⟮c+;after their Max-Age›age or their Expires date has passed⟯, one can ⟮delete⟯ them by ⟮manually moving this into the past⟯. It is also common practice to ⟮set their content to an empty string⟯. 

By default, ⟮cookies⟯ ⟮are only sent⟯ for ⟮requests⟯ for ⟮the FQDN that the cookie was sent from⟯. 
By default, ⟮cookies⟯ ⟮sent from a certain FQDN⟯ are ⟮not included⟯ in ⟮the browsers requests for subdomains⟯. 
Specifying the ⟮`Domain`⟯ property of a ⟮cookie⟯ means ⟮it will be sent⟯ for ⟮requests for the specified FQDN⟯, and ⟮all⟯ subdomains (thus being more permissive than the default!) 
By default, ⟮cookies⟯ are ⟮sent by the browser⟯ ⟮no matter⟯ ⟮the path in the URL⟯ ⟮(c:80;only⟯ ⟮the FQDN⟯ matters). 
If the ⟮Path⟯ attribute is ⟮specified for a cookie⟯, ⟮browsers will only sent the cookie⟯ on ⟮requests for the specified path (or subpaths⟯). 

⟮Cookies⟯ that ⟮originate from⟯ ⟮the same domain as the current domain⟯ ⟮h88;(including ⟮subdomains⟯ if ⟮Domain is set⟯) ⟯ are known as ⟮first-party cookies⟯, all others are ⟮third-party cookies⟯. 

⟮Cookies⟯ ⟮used to maintain the state of being logged⟯ in are known as ⟮authentication cookies⟯ (the whole process is known as ⟮s91:93;c94;cookie-based authentication⟯ ) 
⟮Cookies⟯ used to ⟮maintain the state of an unique user⟯ ⟮with whom to associate browser histories⟯ are known as ⟮tracking cookies⟯. 

The ⟮Secure⟯ property of a cookie means ⟮that it is only ever sent over HTTPS⟯. 
The ⟮HttpOnly⟯ property of a cookie ⟮makes it inaccesible via JS⟯. 
The ⟮SameSite⟯ property of a cookie can take three values, ⟮Strict⟯, ⟮Lax⟯, or ⟮None⟯. 
The ⟮SameSite⟯ property uses a definition of ⟮Site⟯ which consists of ⟮the registrable domain name⟯ and ⟮scheme⟯ (which ⟮can only be http or https anyway, since cookies are a HTTP-only concept.⟯) 
Cookies with ⟮SameSite=Strict⟯ are ⟮only sent⟯ when ⟮the site (registrable domain name + scheme⟯) ⟮the request is being sent to⟯ is ⟮the same as the site of the cookie⟯, i.e. ⟮not on cross-site requests⟯. 
Cookies with ⟮SameSite=Lax⟯ are sent ⟮in the same circumstances as SameStrict=Strict⟯, plus on ⟮cross-site requests⟯, if ⟮the request is a browser navigation one (not e.g. for resources only⟯). 
Cookies with ⟮SameSite=None⟯ have ⟮no cross-site restrictions⟯, but ⟮Secure must also be set⟯. 

The JS inteface for ⟮cookies⟯ is ⟮document.cookie⟯ 

A ⟮zombie cookie⟯ is a cookie that ⟮is restored even when deleted⟯, by using ⟮various nooks and crannies of different internet technologies.⟯ 


##### Content Negotiation

Content Negotiation is a mechanism of HTTP that allows serving different versions of a document at the same URI depending on the prefrences of the user agent.
The headers for content negotiation are Accept and Accept-Language, Accept-Charset, Accept-Encoding

#### CDN

CDN = content delivery network or content distribution network
A CDN is a geographically distributed network of servers. 
The goal of a CDN is to provide high availability and performance by distributing the service spatially relative to end users.
unpkg|FOSS|npm pacakges
jsdelivr|FOSS|different platforms

### telnet/ssh

SSH = secure shell
Telnet is a protocol that sends text plainly and immediately as 8-byte ASCII characters, with the high bit unset.
the SSH protocol, in contrast to the telnet protocol and the various rsh commands/protocols, is encrypted (via public-key cryptography).
SSH is a protocol whose main purpose is accessing the shell on other computers.
In accessing the shell on other computers, the SSH protocol has replaced rsh/telnet.
Besides accessing the shell on other computers, the SSH protocol allows for other network services, such as data transfer.
The berkeley r-commands are a suite of commands and associated protocols that are variants of well-known commands, but may be run remotely.
The berkeley r-commands all start r.
In doing various things on remote hosts, SSh has replaced the various berkeley r-command.
Specifically, to copy data between remote hosts, the scp command running over SSH has replaced rcp.
The berkeley r-commands, telnet and now SSH all have a client-server architecture.

SSH-commands allows using a short user@hostname form isntead of a full URL.
scp is cp (same syntax etc.) but remotely using SSH.
For scp, when using user@hostname, add the file with :filename to the end\

ssh-keygen manages keys for SSH.

### NIS/YP

YP = Yellow Pages
NIS = Network Information Service
NIS and YP are the same thing, just that YP was trademarked in GB and hence NIS.
NIS/YP is a protocol for sharing configuration files between computers.
domainname shows or sets the NIS/YP (!) domain nime
aliases for domainname: nisdomainname, ypdomainname
dnsdomainname shows the systems DNS domain name (the part of the FQDN)

### DNS

DNS|Domain Name System
the problem that both the hosts file and DNS want to solve is mapping hostnames/domain names to IP addresses.
the hosts file came about in the ARPANET era, where it was manually shared and updated.
DNS superceded the hosts file for the most part.
Today, the hosts file is used in some network bootstrapping, but mainly as a resource for internet resource blocking/redirection
To use the hosts file to block something, set its IP address to 0.0.0.0
hosts-file ::= {‹hosts-line›‹linebreak›}
hosts-line ::= ‹ip-address› ‹hostname›{ ‹hostname›}

#### dig

dig is a CLI utility to look up DNS records.
dig-command ::= dig {‹option›}[ ‹DNS-server›][ ‹resource-name›][ ‹record-type›]{ ‹query-option›}
query-option ::= +‹query-option-name›

dig defaults to the DNS specified in /etc/resolv.conf if none is specified.
dig defaults to type of A if the record type is not specified

query option names
short|very short output
noall|don't show any of the sections
answer|show the answer part of the response (only has an effect if answer has been hidden e.g. with noall)

In digs output, non-records begin with ;;, non-records do not.

8.8.8.8|Google DNS nameserver

### WebSocket

WebSocket is an application-layer communications protocol with client and server APIs.
WebSocket, being an application-layer protocol, is distinct from HTTP, but uses the same TCP ports, mainly for firewall-related reasons
WebSocket, in contrast to HTTP allows full-duplex communication and streams of data
WebSocket use the scheme `ws:` (if unencrypted) or `wss:` (if encrypted)
To change from HTTP to WebSocket, the WebSocket handshake uses the HTTP Upgrade header

#### client

on the client side, sockets are created via the `WebSocket` constructor
the `WebSocket` constructor recieves the necessary argument of the url, and an optional argument of which sub-protocols to use
to send data on a `WebSocket`, use the method `send()`
To ⟮react to incoming data⟯ ⟮event handlers are registered⟯ on the WebSocket object
the four common events a `WebSocket` might recieve client-side are open, message, close, error

#### server 

the most common node web sockets library is `ws`

### DHCP

DHCP = Dynamic Host Configuration Protocol
DHCP is a protocol used for automatically assigning IP addresses and other parameters.
DHCP is an application-layer protocol using UDP as the transport layer
DHCP follows a client-server model
the four stages of DHCP operations are often abbreviated DORA
DORA = ⟮DISCOVER⟯, ⟮OFFER⟯, ⟮REQUEST⟯, and ⟮ACK(nowledge)⟯
The DHCP messages (e.g. DISCOVER) may also be referred to by prefixing  DHCP (e.g. DHCPDISOVER)
In general, a ⟮client⟯ sends a ⟮DHCP⟯ ⟮DISCOVER⟯ request ⟮on startup⟯ and then ⟮periodically before it expires⟯
The ⟮DHCP⟯ client sends its ⟮DISCOVER⟯ and ⟮REQUEST⟯ messages as a ⟮broadcast⟯ initiallty, for ⟮renewal⟯ it may also use ⟮unicast⟯
On recieving a ⟮DISCOVER⟯ request, the ⟮DHCP server⟯ uses ⟮its policies⟯ to decide which if any ⟮IP address to assign⟯, and sends back an unicast message ⟮OFFER⟯
A client can receive DHCP offers from ⟮multiple servers⟯, but it will ⟮accept only one DHCP offer⟯
In response to the DHCPOFFER, the client replies with a DHCPREQUEST message, broadcast to the server (can be unicast if renewal), requesting the offered address.
After the client ⟮obtains an IP address via DHCP⟯, it should ⟮probe the newly received address⟯ (e.g. with ⟮ARP/NDP⟯) to prevent ⟮address conflicts caused by overlapping addresses⟯

client         server
  |               |
  |---DISCOVER---→|
  |               |
  |←----OFFER-----|
  |               |
  |----REQUEST---→|
  |               |
  |←-ACKNOWLEDGE--|
  |               |
