
## Web Speech API

Web Speech API: text to speech/speech to text

## Web Audio API

## PWA

PWA|Progressive Web App
PWAs should work to some extent even when ⟮there is no internet✫SpStAtUk8Zp5iwi9yqKP.jpg✫⟯ the ⟮screenshots⟯ property of a web app manifest allows for ⟮previewing images of the web app when installing⟯
for a PWA to be installable, you need to have the web app manifest (with required fields filled in), and a service worker (chromium only) (also an icon and HTTPS, but these are kinda obviosu)

### service workers

⟮Service Workers⟯ are a type of ⟮Web Worker⟯
The main problem ⟮service workers⟯ are solving is handling ⟮loss of connectivity⟯
The ⟮service worker's⟯ ⟮lifecycle⟯ is separate from ⟮your webpage's⟯

The first step in a service workers lifetime is navigator.serviceWorker.register(path-to-service-worker.js), which returns a promise
The service worker's scope ( which fetch events it reacts to) is determined by the directory the script implementing it is in 
e.g. /sw.js has the scope of everything in the project, while /example/sw.js has the scope of everything in /example.
The service worker adds event listeners like so: self.addEventListener...
⟮Workbox⟯ is a library that ⟮bakes in a set of best practices⟯ and ⟮removes the boilerplate⟯ every developer writes when working with ⟮service workers⟯.

## wasm

wasm = web assembly
WebAssembly is a low-level assembly-like language with near-native performance.
Most big compiled languages can compile to web-assembly.
In essence, WebAssembly runs in a low-level virtual machine
A WebAssembly binary is called a module
A wasm Module itself is stateless, and uses a Memory and Table for state. 
Together, a wasm module + memory + table are an Instance
a wasm Table is a typed array of references (e.g. to functions) 
a wasm Memory is a linear array of bytes used for storage
wasm page size = 64k
wasm memory can only be grown by a multiple of the page size
wasm memory cannot be shrunk
By default, as of 2021, the wasm interface only accepts numbers (and pointers) as types

wasm modules|.wasm
wasm textual representation|.wat

wasm-bindgen for rust generates glue and polyfills things so that we can use a bunch of types of features that we couldn't otherwise.
wasm-pack is a tool for helping integrating rust wasm with your webdev workflow.
AssemblyScript is a TypeScript-based programming language that is compiled to WebAssembly.
