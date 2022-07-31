
# the web

WWW = World Wide Web
The WWW runs on the internet, using the protocol HTTP(S).
The WWW is only one of many technologies running on the internet.
A web browser is a program to access the WWW.
The WWW was developed in CERN in 1989 by Timothy Berners-Lee.
The first web browser was written in 1990, the WWW was released in 1991.
The main organization working on web standards is the W3C.
World Wide Web Consortium = W3C
A web site is a collection of web pages, generally one that share a domain name/FQDN

## user agents

User agent may mean any device that accesses web services for an user, or autohyponymously to a web browser specifically, or to the HTTP header User-Agent.

lynx, w3m|text-based browser

Qutebrowser is a vim-like browser written in python.
In qutebrowser, quickmarks are bookmarks that have a short name
For qutebrowser, you do ⟮advanced config⟯ in ⟮the config.py⟯ 
In the config.py of qutebrowser, you ⟮can change most settings⟯ ⟮on the `c` object⟯ 
In qutebrowser, greasemonkey scripts become active merely by placing them in $XDG_CONFIG_HOME/qutebrowser/greasemonkey

## file-sharing

ephemeral file-sharing sites allow you to upload files which expire after a while

## performance

https://developer.mozilla.org/en-US/docs/Web/Performance/Critical_rendering_path
https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading
TODO: More structure. How do these relate? WHat aspect of performance are they optimizing? Perhaps use PRPL as a structure, or something else, or a combination.

### speculative parsing

Speculative parsing is that the browser will not block when hitting a script tag, but instead just continue parsing while fetching the script, and using the parsed DOM if the script hasn't modified it (which only really happens via document.write()).
Speculative parsing does not apply to images/css/videos, which will not block even if speculative parsing is disabled (the fact that it doesn't is a common myth)

### lazy loading

lazy loading is loading things only when needed.
In general, one lazy-loads the things that are not critical to performance.
To enable lazy loading for images and iframes, set loading="lazy", these images will only load once they are a specific distance away from the viewport.
TODO relationship with code splitting (I think code splitting allows for lazy loading)

### server push

Server push allows the server to send along resources it knows the browser will need directly on the first HTTP request (without the browser having requested them)
Server push is a feature of HTTP/2, used by specifying it in the HTTP header

### minifcation

⟮Minifying⟯ is ⟮removing unnecessary characteristics⟯ (e.g. ⟮longer names, whitespace⟯) from ⟮source code⟯ to ⟮reduce size⟯
⟮minified files⟯ are commmonly indicated by ⟮.min(.whatever)⟯

### media compression

Images used ⟮on the web⟯ are typically ⟮specifically compressed⟯ beforehand, e.g. ⟮by using programs such as imageoptim⟯

Image compression tools
|GUI|CLI|API|other
imageoptim|y|y|y
squoosh|web|y|n
sharp|n|n|n|npm module

### PRPL

Push/Preload the most important resources
Render the initial route ASAP
Pre-cache remaining assets
Lazy-load other routes and non-critical assets

the "render the initial route ASAP" of PRPL is basically "reduce time to first (contentful) paint"
"render the initial route ASAP" can be achieved server-side by SSR/Static Generation, and client-side by stuff like async or defer (and maybe others)

#### P

⟮c+;‹link rel="preload"⟯ specifies that you ⟮will need the resource very soon⟯, and that it should be downloaded ⟮asyncly⟯ with ⟮high priority⟯
⟮c+;‹link rel="preload"⟯ needs an ⟮as=⟯⟮"kind(e.g. style, script, image)"⟯
If you've specified a resource with ‹link rel="preload", you still need to actually include it later

### defer ＆ async

defer ＆ async are two attriubtes for ‹script› that influence how it is loaded.
Ignoring speculative parsing, when the browser hits a ‹script› tag, it blocks until it's loaded, which is not ideal since scripts are quite large, and the browser could be loading things in parallel.
Instead of the default behavior, the `defer` and `async` attribute of scripts tells the browser to load the script in the background.
Between  the `defer` and `async` attributes, defer executes scripts loaded in the background ⟮when the dom is fully built⟯, in the order they were in the document
Between  the `defer` and `async` attributes, async executes scripts loaded in the background ⟮as soon as possible⟯, in the order in which they load, no matter source order.

### RAIL

RAIL is a performance model that centers on the user.
RAIL is short for Response, Animation, Idle, Load.
RAIL's perfomance model consists of goals for the four things of which it consists.
Response|respond to user input within 100ms. To account for other background tasks, budget 50ms.
Animation|provide an animation frame every 16ms (= 60FPS). Since browsers take about ~6ms to render a frame, budget max 10ms to calculate the frame. 
Idle|Use idle time so that other goals are met. Perform work in idle time in bursts of 50ms or less so that the Response goal is met.
Load|(subject to change with new technology) Load within 5s on first load and in 2s on subsequent loads on mobile.

### minification

Webpack minifies your JS by default, using `terser`.
Source maps allow mapping minfied/compressed/otherwise transformed code back to the original source
to indicate a source map, at the bottom of the optimized file, add a magic comment or use the http header
source map magic comment: //# sourceMappingURL=foo/bar.js.map 
Most dev tools have source map support built in.

### Google speed

PageSpeed Insights|Lab data ＆ realworld data|Web Vitals|only website by default
Lighthouse|only lab data|Web Vitals ＆ other data|GUI (devtools ＆ website), CLI, CI pipeline

#### Lighthouse

Lighthouse's Performance audits provides a grade consisting of (the scores of individual) metrics, but also offers opportunities and diagnostics::d... as ways to improve the metrics
Lighthouse consists of 5 categories, Performance, PWA, Best Practices, Accessibility, and SEO.

⟮Web Vitals⟯ are the stats that ⟮google⟯ measures to judge ⟮the user experience of your websites⟯
⟮Core Web Vitals⟯ are the subset of ⟮Web Vitals⟯ that ⟮apply to all web pages (and are thus considered very important)⟯
as of 2020, there are 3 core web vitals

Largest Contentful Paint, Cumulative Layout Shift|Core Web Vitals ＆ Lighthouse Metrics
First Input Delay|Core Web Vitals 
First Contentful Paint, Speed Index, Time to Interactive, Total Blocking Time|Lighthouse Metrics

A ⟮layout shift⟯ is when a ⟮visible element⟯ ⟮shifts position⟯ between ⟮render frames⟯ (in bad cases causing users to e.g. ⟮click the wrong button⟯)
⟮Cumulative Layout Shift (CLS)⟯ is how google measures the ⟮badness⟯ of the ⟮layout shifts⟯ you've going on
The ⟮largest contentful paint⟯ is when the ⟮largest media/text block⟯ (which elements are exactly considered is more complicated) loaded, relative to ⟮when the page first started loading⟯


a ⟮long task⟯ is when ⟮the main JS thread⟯ is ⟮blocked⟯ for more than ⟮50ms⟯
⟮Total Blocking Time⟯ as a Lighthouse metric measures ⟮cumulative length⟯ of ⟮long tasks⟯ between ⟮First Contentful Paint⟯ and ⟮Time To Interactive⟯
the ⟮Lighthouse Speed Index⟯ is how quickly ⟮the viewport is visually populated with content⟯
⟮Time to Interactive⟯ as a ⟮lighthouse⟯ metric is the time it takes for a page to ⟮become fully interactive⟯

CLS  Cumulative Layout Shift 
FCP  First Contentful Paint
FID  First Input Delay
LCP  Largest contentful paint

## web analytics

In web analytics, a bounce is a person who only views one page of a site and then leave.
The bounce rate is the percentage of total site visitors who bounce.

## platforms running on the web

### search engines

#### google

WIthin google search, ⟮tbm⟯ is the key of the query parameter that ⟮specifies the type of search (Image, News, Shopping etc.⟯) 
For example, ⟮Specifying the search mode in google search as images⟯ is done by ⟮`tbm=ish`⟯ 
Force google to ⟮only finde pages from a certain domain⟯ is done by ⟮site:foo.com⟯ 

### fora

#### text ＆ imageboards

A ⟮textboard⟯ is a ⟮simple⟯ kind of Internet ⟮forum⟯; most require neither ⟮registration⟯ nor ⟮entry of a screen name⟯. 
An ⟮imageboard⟯ is like a ⟮textboard⟯, just with ⟮images⟯. 
⟮Textboards⟯ as well as ⟮imageboards⟯ were invented in ⟮Japan⟯. 
⟮Textboards⟯ such as ⟮2channel⟯ are generally popular in ⟮Japan only⟯, while ⟮imageboards⟯ (e.g. in the form of ⟮4chan⟯) are popular in ⟮english-speaking countries too⟯ 
