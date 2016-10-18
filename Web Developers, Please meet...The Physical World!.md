**Web Developers, Please meet...The Physical World!**
-----------------------------------------------------------
*With Jean-Philippe Côté*

Even though HTML, CSS and JS were super basic back in the day, Jean still remembers the feeling of creating something with just a bit of code. The excitement faded after time as web development became more of a business, but in the past couple years JS – that clunky old language – gained a life of its own. Jean realized that the language could be used to not only to push pixels, but also real life objects. Jean’s goal is to demonstrate that we can use the skills we already have to interact with the analog world.

The term "physical computing" more broadly describes what Jean working on, than the term "experiential design". Physical computing encapsulates IoT, interactive installations, robotics, wearables, and interactive tangible medias. It is all these things and ultimately depends on what we want to achieve. The wikipedia defines it as “building interactive physical systems by the use of software and hardware that can sense and respond to the analog world”. The key words there are “software”, “hardware", “sense" and “respond”. If you want to build a robot, you obviously need hardware, you need to control that hardware with software, you’ll need to give a sensor so it doesn’t bump into things, and it needs to respond to that sensory inputs. But can we build something like this with front-end tools? Yes!

* To build robots, use[ johnny-five.js](http://johnny-five.io/)

* For home automation, use[ heimcontrol.js](https://ni-c.github.io/heimcontrol.js/)

* For interactive art, use[ p5.js](https://p5js.org/)

If you dare, you have a whole new area of expertise at your fingertips. And the good news is that the craft of physical computing is more and more in demand – if creating a robot isn’t cool in and of itself and motivation enough.

So let’s start. The Arduino is a microcontroller that is open source, cheap, has a great community, and tons of add ons and lets you access hardware with an input and output mode. To get it to talk to HTML, CSS, JS we first need to install some software, "firmata" that allows the Arduino to understand the firmata protocol. You just need to do this once and you’re good. Then use johnny-five.js for the robotics/physical computing library, but beware that it is a Node library. If you haven’t used Node, know that it is javascript outside the browser. Johnny-five doesn’t give you HTML and CSS though, and for that you need NW.js which uses Chromium and is a full NodeJS environment so you can use everything that comes with Node along with your other front-end tools. This set of tools, NW, Johnny-five, and the Arduino, is called the NJA or ninja tool chain. 

