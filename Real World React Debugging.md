**Real World React Debugging**
-----------------------------------------------------------
*With Jared Forsyth*

[Khan Academy](https://www.khanacademy.org/) was the first production use of React with something like 15,000 components – debugging became very important very quickly. The job of debugging tools is to shed light on the computer black box. Some ways to fix bugs take more effort than others and you need to judge if they are worth the investment based on the size of the codebase and team. 

**Default warnings**

React by default will flag some errors and give you some warnings, which are helpful for highlighting issues that could indicate deeper problems. If you hit some of these warnings, e.g. "Failed prop type" look for the filename and line number (you’ll need jsx-source). Some errors don’t give the line number right away but you can open the stack trace and look at the render method to find the line number. There are some warnings that are more complicated, where the error has to do with the state of the app at that point. In that case go to where the warning is triggered, add a breakpoint, then reload the page, then in the call stack jump to the render method to find the line number.

**Debugging**

We shine a line even further with React developer tools ([https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)). With React DevTools when you select a component in the hierarchy you view and change its  properties and state in Props and State tabs. This can be very useful for getting an overview of all the properties of a component and seeing how they change. If you need more control, you can access the instance of the selected component by typing $r in console. You can use $r to dig further into and change component state. Note that in the hierarchy view red triangles indicate which components are stateful. React devTools can also help you figure out why something is slow by checking the "trace react updates" box. This shows you which and how much other components are affected when you do something on the page. The affected components are given a colour outline reflecting the time between updates: the shorter the updates the redder the colour.

**Catching bugs**

Just fixing bugs isn’t enough; you need to know where the bugs occur too, and for that you need a process – a net with which to catch the bugs. We *could* just use users for catching bugs, but most of the time you'll want to catch them before they go out. As this requires some effort, evaluate if its worth it first. If it’s a side project or you’re just getting started, it’s probably not worth it, but if many people are touching the code, you plan to support it for a while, or have a lot of production users it’s worth the investment.

Automated testing is the most time intensive way to catch bugs. Automated testing gives us a way to verify complex behaviour, e.g. an algorithm. The other use is regression testing, to make sure that necessary behaviour is retained, e.g. is your sign-up button the page is still there. This is really brittle, however, especially is you meant to change the sign-up button. For regression testing with less hassle try fixtures (jsx.fixtures.js). With Jest snapshot tests you provide an example of how you are going to instantiate your component and run the jest before submitting the code. Jest diffs and shows you snapshots of  how it affects other places the component is used. Visual regression test can be fairly finicky however. For example. Chromes isn’t deterministic in the way in renders SVGs and visual regression will catch the noise in how they are rendered in Chrome.

**Preventing bugs**

Figuring out where state should live is still a hard part of UI and make consistent decisions about who owns that state can help prevent bugs. If you are keeping track of a state change and then telling the parent about it, then the parent should actually own that state. The reverse is also true. Another way to have code that is less bug prone is to take logic out from presentation. If you’re doing something that’s more than a few lines, pull it out as a pure function and test it separately. This will mean less tests for your react components overall.

In summary, follow best practises to avoid bugs, use tools to catch bugs before they hit your users and use React Devtools to fix them. 

