What The Heck is WebAssembly, And Do I Have to Learn C Now?

With Dan Callahan

Link to slides, demos and related materials:

[https://callahad.github.io/webu16-wasm/](https://callahad.github.io/webu16-wasm/)

What is WebAssembly?

1) Compiler target for the web. Not a programming language of it’s own, rather does compilation of C to the web.

2) Virtual ISA - gets you as close to physical machine instructions as safely allowed.

3) Javascript feature - efficient loading/caching of large programs - can replace js functions with C variations for performance improvements.

Why WebAssembly? What are some use cases?

* Client-side image compression - Facebook does this on profile pics

* Facial recognition

* Cryptography

* Media decoders

* Games

* Simulations

WebAssembly lets you opt out of garbage collection and let’s you manage memory.

4) Evolution of ASM.js

* Avoid plugins

* Port large applications

ASM.js ships with Firefox and Edge and is under development for Chrome and Safari. The major limitations of ASM.js are large file sizes and long parsing times.

The first release of WebAssembly set a goal of being an improvement over ASM.js. WebAssembly already is shipping in Firefox, Chrome and Edge. Development is shipping features iteratively and an API is available to allow for testing of available features.

* ASM.js is available as a fallback

* Data can be shared back and forth between a wasm app and Javascript

* Eventually you’ll be able to import wasm apps using ES6 modules

To give an idea of the improvements created by WebAssembly over ASM.js, check out the Unity based demo of Angrybots. In ASM.js app is 20MB. That goes down to 6MB in WASM and if you gzip that it goes all the way down to 3MB.

Pypy.js is a project that uses ASM.js to allow Python to run in the browser. This already runs the Python app twice as fast than if you run the code locally. This is expected to get even faster once it’s running in WebAssembly.

Microsoft has a chess AI demo that pits unoptimized code against the ASM.js version. The latter always wins as it can search far deeper in the 2 seconds per turn time limit imposed by the demo.

WebAssembly will eventually sit at the same level as Javascript. Along with use of CORS it will be able to access various Web APIs.

To compile to WASM you currently use the ASM.js tool chain, though eventually you’ll be able to compile it more directly. Updates to the current available tool chain are expected to ship, at a minimum, in Firefox by January 2017.

Will WebAssembly replace javascript? No. Js has too much momentum and too large of an ecosystem. It will however, change what the web can do. For example, typically we’ve had to wait for new media codecs to be implemented in a particular browser, but now with WebAssembly you could actually ship a decoder with your assets.

