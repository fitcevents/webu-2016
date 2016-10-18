**Front-end developers can make games too!**
-----------------------------------------------------------
*With Alicia Sedlock*

Alicia is web developer in Boston working at [Society of Grownups](https://www.societyofgrownups.com/), who doesn’t understand why people hate CSS. She was exposed to games by Newgrounds, which was a popular hub for Flash animations and games. There was a game called, "[The Binding of Isaac](https://en.wikipedia.org/wiki/The_Binding_of_Isaac_(video_game))", that started at a game jam and was continued afterward. Three months later the team had a full Flash game released on Steam, and a demo version on Newgrounds. The game became extremely popular. It was an example of the power that Flash had for developers back in the day.  Alicia realized then that the web was meant for more that just the sharing of documents – it was an artistic medium and capable of so much creativity. And then Flash died. (Or was murdered depending on who you ask.) Other stuff came up, like video, but there were no niche for memorable, creative things again for a while...

Then one day, "[Cookie Clicker](http://orteil.dashnet.org/cookieclicker/)" appeared. It was an insanely addictive game, and, when page source was viewed, turned out to be just a bunch of nested divs and some javascript, with an accessible global "Game" object that could be “hacked” in the javascript console. This was the first true web game Alicia had seen since Flash. Then another notable example appeared, “[Depression Quest](http://www.depressionquest.com/)”, which developed to help those coping with, and educate those without depression. It pushed people to get help and was a game anyone can play. Depression Quest was built with an engine called Twine, a web-based engine for narrative platform and was released on Steam.

Alicia went to her first game jam intending to build games with the tools she knows: front-end developer tools and created "[Horse combat for horsemanity](http://horsemanity.herokuapp.com/)", using straight-forward HTML, CSS and JS. For her second game “[Grandma made too much cake](https://grandmamadetoomuchcake.herokuapp.com/)”, it’s just drag-and-drop divs with jQuery and hittest.js, which does the calculations to detect if you’ve hit the boundary of PNGs.

**Front end developer tools that you can use for games**

* You *can* make games with just **CSS** and **HTML**, but should you? (The CSS will be *very* complex.)

* The poster child for front-end games is **canvas**. Mozilla has excellent docs for creating games with <canvas>. Because in <canvas> the objects actually are the shapes that they are, it makes collision detection much easier that PNGs in divs. 

* Another key technology for games are **web sockets**, with a "little library" called socket.io. You can listen to players joining, and emit events on player movement that others can listen to. Anything you can draw in canvas you can put into event emitters. See "[Supersyncsports](https://chrome.com/supersyncsports/)" for an example of a game running on web sockets. 

* Another technology for making games is **WebGL** (look out for WebGL 2 coming out soon). WebGL is for you if you like 3D, math, and physics, and have time. One example WebGL game is[ roTopo](https://rotopo.com/). 

* There’s a javascript API, **[gamepad AP**I](https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API/Using_the_Gamepad_API), that lets you connect to gamepad controllers like the Xbox controller and map keyboard keys to the 16 Xbox buttons available. With the gamepad API you have to check every single frame if a button is being pressed or not, which is tedious. Happily, there is a library, gamepad.js, which gives you a more succinct syntax for interacting with the gamepad – you don’t need to manually keep track of frames. Always make sure you have a fallback to keyboard though! 

* **Game engines** of interest: Phaser, Bogart (recently released by Bocoup for games in React, which according to Alicia, is a match made in heaven).

* Nintendo has a[ Nintendo Web Framework](https://wiiu-developers.nintendo.com/), but the development kit is expensive.

* Also, look out for **WebVR **games soon.

Making games on the web is good for the web: it pushes technical boundaries which pushes hardware boundaries. *And* you can make money from them. There are interesting challenges if you want to monetize since the code is "open", but you could deploy with Cordova, or run your game on the desktop with Electron.

Games are coming back to the web in a big way.

