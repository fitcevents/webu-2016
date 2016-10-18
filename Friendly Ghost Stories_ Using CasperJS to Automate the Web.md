**Friendly Ghost Stories: Using CasperJS to Automate the Web**
-----------------------------------------------------------
*With Engin Arslan*

[http://enginarslan.com](http://enginarslan.com)

Phantom.js can do nearly anything a browser can do, but it’s headless. Ie. you can use it to run a Bing search and return json, or visit an array of url’s and return screenshots of each.

It can:

* Navigate the web

* Capture resources

* Monitor network requests

* Do testing

CasperJS is a wrapper for Phantom.js that adds a lot of utility functions. It integrates promises to ease the development of web navigation code.

CasperJS requires:

* Python

* NPM

* [Phantom.js](http://phantomjs.org/) (recommended you install via NPM, local to project, not global)

Add [CasperJS](http://casperjs.org/) to your package.json and you are set.

CasperJS is Webkit based NOT Node.js based despite that many of the common API’s look similar. 

You can terminate a casper script using: casper.exit()

If you are using casper.run() it implicitly exits unless you provide it a callback.

CasperJS operates with two contexts:

script context = the logic of your CasperJS code

page context = the code of the page being navigated

Some code examples:

    this.capture(‘url);
    
    title = this.evaluate(func() {
    
      return document.title
    
    }

This will get the document title from the page context - using this approach you can only return jsonable data from the page context.

    casper.on(remote.message, function() {
    
      console.log("remote message: “ + msg);
    
    }

This will let you return console logs from the page context.

Examples of CasperJS’ convenience methods:

getTitle()

getCurrentUrl()

getHTML()

evaluate() has no knowledge of scope outside the page context thus you need to explicitly pass data into page context if needed.

waitForUrl()

waitForSelector()

waitForText()

These are all ways that you can specify items within the requested document that you need to wait for before continuing the navigation script.

One important note, if you are loading google.com be aware that it returns different html to headless browsers. Two approaches to dealing with this:

* Change the user agent provided by CasperJS

* Get the user agent of CasperJS and using Devtools to alter Chrome’s user agent, browse Google and use that source to model you navigation code

Ergin found that the latter option netted better results.

CasperJS can inject remote scripts into a page. For example, you might inject JQuery so that you can use jQuery selectors to make it easier to find stuff in the document.

