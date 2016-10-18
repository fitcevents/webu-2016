**Performance: Beyond your Portfolio**
-----------------------------------------------------------
*With Luke Dewitt*

**The RAIL Model** - Google’s yardstick for performance: Response, Animation, Idle, Load

**Response**

* Jakob Nielsen’s Response Times (20 years ago):

    * .1 s = instantaneous reaction

    * 1s = uninterrupted flow of thought

    * 10s = user’s attention

* BOTTOM LINE: People want to see your website now! You can’t afford to have a slow site. "There’s just no attention span anymore"

* 100ms = lag

    * People need immediate reaction (and should have substance) -> a.k.a. user perceived performance

**Animation**

* 60 fps

    * Target fps rate for UI animation

    * This means you have 16ms to react (to the user)

**Idle**

* Simple tasks

* Aim for <50ms

**Load**

* You don’t need everything to load in a site in 1s.

* Your site must load in < 1s

* Focus on critical path rendering and user perceived performance

**Critical Path Rendering**

* Shoehorn your critical path CSS (the content that you see above the fold)

* Eliminate render blocking JS

* Image optimizations (e.g. use tiny png, responsive images via srcset attribute)

* Lazy loading images 

* File compression (with Gzip)

* File Delivery

**File Delivery**

* We’re now in the HTTP/2 era

    * Tactics:

        * Concatenate files

        * Inline assets

        * Combine images

        * Domain sharding

* Why HTTP/2 is awesome: It’s a binary protocol. There’s far less of a chance that the browser will mess up

**Header Compression**

* *HTTP/2 requires TLS

**Getting Ready for HTTP/2**

* Not much. It’s almost as simple as flicking a switch on.

