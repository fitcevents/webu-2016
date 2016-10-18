Service Workers for Everyone!

With Ryan Christiani

At hackerYou (where Ryan works) they wanted to create an offline experience for their students that would allow them to review their class notes in spotty internet situations, e.g. on the train and subway. In fact, there’s a lot of content on the web that should simply be accessible offline and service workers are a way to do this. Before service workers we could use app cache, but that’s starting to be removed from browsers and service workers are taking over. Service workers are a new API in the browser that sits between your site and the network (the cloud) and is part of the progressive web app (PWA) technology stack. In fact, it is probably the key facet of PWAs. The goal of PWAs is to get close to the speed of native apps, have push notifications, and the ability to add the app to the home screen. Google has really been promoting the idea this year.

Service workers are a web worker API that allow us to execute code in a separate worker thread. Javascript is a single threaded language and doesg one thing at a time extremely fast. If you want to "do more" in JS you need to cue them up. Check out Philip Roberts' talk, "[What the heck is the event loop anyway?](https://www.youtube.com/watch?v=8aGhZQkoFbQ)” for a review of how JS does things one at a time. With web workers we can do additional things in a separate thread, which make them ideal for heavy computations. Check out[ pokedex.org](https://www.pokedex.org/) as an example of using service workers and push notifications, and the blog about how it was created.

**How to get started**

First we need to register our service worker by check if web workers are available then registering a file. To check if it’s been register, look at the Applications side bar in devTools. Within the service worker we no longer have access to the DOM – it is a completely different environment. Once we register it, it goes through a few life cycle events, which we can listen to. We can hook into the install event and start caching static assets there: inside the service worker, attach an event to install, call caches and use the addAll() method to cache out static assets. Back in the Application panel, we can look at cacheStorage to see our now cached assets. To tell the service worker to act as an intermediary we need to use the fetch() method, which will use the service worker if the browser does not detect an internet connection. To set this up, attach an event listener for the fetch event and use the respondWith() method to check the cache and return content. (For recipes see Jake Archibald’s[ blog posts](https://jakearchibald.com/2014/using-serviceworker-today/).) We can get way more complex than this too. For example, we can set things up so that if we look up content in the cache and isn't a match we can tell the browser to go to the network to and get it. Then we can put that content in the cache so in future we don’t need to go to the network. Check out Jake Archibald’s, "[The offline cookbook](https://jakearchibald.com/2014/offline-cookbook/)" for many more helpful service worker patterns, as well as[ SW-toolbox](https://googlechrome.github.io/sw-toolbox/docs/releases/v3.2.0/) from Chrome.

**Caveats**

This is perfect for content that doesn’t change a lot, but what about frequently updating content? If we are connected to the internet we want to get it from the internet and only if that fails pull from cache. The data we pull from cache might not be the most relevant data but at least it’s *something*. Basically, we can customize our service worker to specify which content you should always try to go to the network for, and which you could retrieve from the cache. (Note that the code for this is promises "all the way down".) Eventually we’ll want to clean up our cache however, so it’s important to version your data, and listen to the activate event to periodically delete caches.

**Debugging**

The new application tab in Chrome is your friend. It gives you a look at all the things that are happening in terms of service workers. To unregister service workers you don’t want: Application > Service Workers > check, "Show all" and click to unregister them. Note that you’ll want to build your site almost completely before throwing the service worker in or you’ll need to be constantly clearing your cache as you develop. Be for-warned, an error you might see a lot is the not-so-helpful, “an unknown error occurred when fetching the script" 

**Browser support**

Browsers across the board are interested, but it’s still mostly a Chrome and Firefox experience. Use the[ HTML Worker Test](https://nolanlawson.github.io/html5workertest/) by Nolan Lawson to see which APIs are available in different browsers. 

