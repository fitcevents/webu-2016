**Getting Started With Getting Started With Jekyll for Static Sites**
-----------------------------------------------------------
*With Brian Rinaldi*

Brian has published the free [Static Site Generators](http://www.oreilly.com/web-platform/free/static-site-generators.csp) for O’Reilly and is currently co-authoring a book, "Working With Static Site Generators" for O’Reilly with Ray Camden.

[http://developer.telerik.com/featured/getting-started-with-jekyll](http://developer.telerik.com/featured/getting-started-with-jekyll)

The core advantages of a static site versus something running on php, node.js or what have you is that they are:

* Fast

* Secure

* Flexible

They are good for building content heavy sites, with infrequent updates (once a day at most).

There is no additional processing required on a server, it’s simply reading an html file and sending the contents to the client. Also, without any server side scripting or database involvement the site is extremely secure. Finally, they are very flexible as you are not constrained by the limitations of any framework.

It use to be tedious to build static sites. Maintaining and updating a large site could be very challenging. Static site generators have been developed to alleviate these problems.

The basic idea is that you take a bunch of source files such as markdown, yaml, sass, coffeescript, handlebars templates, etc, then run them through a static site generator. This will spit out html, css and js files that are ready to be placed into production.

If you head over to [http://staticsitegenerators.net](http://staticsitegenerators.net) you’ll find +430 tools for generating static sites. There are can sort the list to see the top generators where you’ll find:

* Jekyll - Ruby based

* Hugo - Golang based

* Hexo - Node.js based

* Pelican - Python based

* And many many more…

## So why choose Jekyll?

It’s the most mature of the generators available - it has the most robust tooling, imports and helpers. Along with that it has a large and established community.

It has integration with Github pages, allowing you to publish your static Github pages using Jekyll. [https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/#keeping-your-site-up-to-date-with-the-github-pages-gem](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/#keeping-your-site-up-to-date-with-the-github-pages-gem)

A large community means there are lots of existing templates and plugins to choose from. Jekyll has decent documentation, band broad support. Even though it’s Ruby based, you (probably) don’t need to learn Ruby. You really only need to use Ruby for doing documentation.

## Getting Started

Visit [https://jekyllrb.com/](https://jekyllrb.com/) for details, documentation, etc.

### Prerequisites

* Ruby

* Rubygems

* MacOS or Linux (there is no official support for Windows, by it is possible)

As of El Capitan, Apple has messed up Ruby so now you need to use Homebrew or similar to install Ruby.

To create a new site:

* jekyll new sitename/path

* cd sitename

* jekyll server

 

This will create a base site and some templates for you, then launch the site on [http://localhost:4000](http://localhost:4000)

You can create a basic config using a yaml file. You can add whatever key:value pairs you need.

Using a templating language with a generator is pretty important. By default, Jekyll uses [Shopify’s Liquid](https://github.com/Shopify/liquid) templating language. Liquid has nice filters for things like date formatting, markdown formatting, etc. Can do standard logical flow: includes, conditionals, loops. Loops have nice additions like limits and offsets that help control content output in a template but are missing from many other templating languages. Liquid is also well documented. 

Jekyll has a notion of both pages and posts. Pages are coded in markdown or html and can exist anywhere in your project structure. Posts can also be markdown or html but must be placed in _posts and follow the naming format: YEAR-MONTH-DAY-TITLE.MD (or .HTML).

You also need to include front matter, metadata about the page/post. Ie. layout, title, date, categories. Categories are essentially the route to the page or post. Ie. If your categories for a post are ‘fitc’ and ‘webu’ then the the url for the post will be: /fitc/webu/2016-10-03-mypost.html

You can work with data in multiple formats: yaml, json, csv, etc. These files get placed in the _data directory. Values can be accessed in a template using site.data.[filename]

When it’s time to deploy your site, run ‘jekyll build’ which will generate all the output files into the _site directory. From here you can simply FTP the files to a server, or use something like Glynn to watch the directory and FTP changes. 

Github pages will automatically build Jekyll templates when you commit changes. 

There are services like [Netlify](https://www.netlify.com/) which help manage the build and deployment process of static sites.

You can install [Jekyll Admin](https://github.com/jekyll/jekyll-admin) to get access to a basic markdown editor or use cloud based tools that do the same. All will help you manage the content for your static site.

Want to compare site generators? Brian has built the same site with a pile of them for you to compare. [http://github.com/remotesynth/static-site-samples](http://github.com/remotesynth/static-site-samples)

.

