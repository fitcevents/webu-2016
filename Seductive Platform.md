Seductive Platform

With Scott Biggart

Scott works at Uber on the UberRush service.

What is platform?

Essentially it’s putting together a suite of tools that people need to do their jobs. "We want to build tools for fighter pilots."

The majority of Uber’s web development is for internal tools.

In the beginning Uber was built on two monoliths. The API which provided backend services and the Tools, massive single page app that was used to configure the data via the API. Engineering was divided into two teams, driver side and rider side. The driver side was mostly Python while the rider side was largely focussed on UI and using javascript. Working together was a major challenge. The code base became a mess and people started to just copy and paste services as quick workarounds for problems.

Decided they needed to prioritize restructuring code. We’ve all heard the idea that an ideal project will have quality of software, affordability(number of engineers) and speed(time to feature completion) and that in reality you can only pick two of these. Their velocity was up and down with each feature cycle. They wanted to build a momentum platform. This required a project to be the vehicle for change.

Time for decision making. What are the pillars of engineering for Uber?

* Consistent experience across verticals

* Explicit over implicit - NO magic code!

* Testing & especially monitoring

* Improve performance

They needed to determine a philosophy to drive the decisions. This needed everyone on board and needed to create developer happiness.

Don’t over engineer things. Don’t build things just because you think it’s cool. Don’t build platform for platform. Bring ideas into platform. Fix things that aren’t stable.

Don’t bike shed - don’t have your nuclear engineers spend two weeks talking about the best way to build the employee bike shed.

The Web Platform Team emerged. All teams contribute, but the platform team are the shepherds/advocates for the best practices of building the platform: documentation/tools/techniques.

What to build?

Superfine - Uber’s internal equivalent of Bootstrap. Not open sourced (though they’d like to), suite of React components. Superfine helped enforce a standard Uber look across everything.

Scaffolding - laying the groundwork for all engineers to have a standard way to do things like logging, authentication, monitoring, localization. Ie they built Bedrock using Express to assist with monitoring across the platform.

Regardless of the best practices put forth, all teams are still given the leeway to override any of these approaches if they need to.

How to measure success?

They use an internal cache of npm where they also host their own private modules. They can run counters on this to track module use. They also run regular internal surveys to track feelings about their platform.

Wrote their own linter, UberStandard. Initially it was really strict, but they found this was problematic. Eventually they backed down and instead required all code to be linted, but teams could choose the linter of their choice and set their own standards - so long as they were consistent within their projects about the approach.

Now they write all the front-end code using JSX and ES6. 

